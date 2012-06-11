---
layout: help
title: How do I clean my data?
---

## How do I clean my data?

Most data about government finance that can be acquired needs to be cleaned up in order to be used in an application such as OpenSpending. This is even more true of data that has been extracted from sources such as PDF files, or even paper documents. 

It is hard to describe exactly what needs to be done (and how): the ways in which data can be distorted or irregular are countless, and many of
these errors are not obvious. The following list is therefore
necessarily incomplete but it tries to provide a check list of frequent
issues.

## The OpenSpending Data Format


1. **OpenSpending takes CSV files**: OpenSpending is very flexible with regard to structure, for example, it does not specify the column order, however the content of the columns must be standardised.
2. **OpenSpending requires there to be one header row in the file**: This is what the software will look for to identify the names of your columns. All other rows are treated as data rows.
3. **Rows should contain only one type of information**: i.e. one budget line (or “fact”). In many files, you will see that any individual row contains data for multiple years, as well things such as both budgeted and actual spend. One individual row contains a maximum of one time period, and contrasts have been created within columns. Note that formatting data for OpenSpending often means creating many more rows than were found in the original document.
4. **No blank rows or cells**: Data imported into OpenSpending should be fairly de-normalized: while there may be references to external code sheets/master data, each row should contain all the information required to construct the resulting item. Columns (particularly classifications) should have a value for each row; they will not automatically “fill down”.
5. **No pre-aggregated totals**: (e.g. sub-totals or “roll-ups”) within the data (OpenSpending will do the maths and compute these automatically)
6. **There must be a combination of columns or an individual column which constitutes a ‘unique identifier’** : OpenSpending was built with a view to re-loading entries into the database at any time, even when existing data is loaded. This means that there must be some way to calculate a unique fingerprint for each row in the data which OpenSpending can use to determine whether it should update an existing row or create a new one. The easiest way to do this is to just add a dummy column to the dataset in which you put a number that increases for each row (you can do this in Excel by typing the numbers into the first two rows, selecting both cells and dragging down the lower right
corner of the cell to extend the series).

There are 3 example datasets below to help further:

* <http://wiki.openspending.org/CSV_Format_Example1>
* <http://wiki.openspending.org/CSV_Format_Example2>
* <http://wiki.openspending.org/CSV_Format_Example3>


### Some common problems 

Below are some common patterns with the data and how to fix them:

* **Splitting columns:** Check that each column in your data only contains a single logical value. For example, a time column may include entries like "December 2001 to January 2006". This actually contains two pieces of information: a start and an end date. Try to split these columns up, for example in Google Refine.

* **Fixing inconsistent spellings and values:** Get a listing of all existing values in a column. In SQL, this can be done with the DISTINCT modifier, while Google Refine offers text facets for this purpose. Looking at this list you may note inconsistencies, such as variations in spelling, casing or simply lines of data that have errors. Try to reduce the number of distinct column values as much as possible.

* **Make each line represent only one measurement** A single line of source data may contain information about several years of data or about multiple transactions. For example, a budget document may contain columns like "Year1, Year2, Year3". You need to split this up into three rows with two new columns: "Year" and "Amount". In those cases, you should transpose the dataset across the concerned columns to generate a line for each transaction. This line should share all the remaining (common) data of the original line. Google Refine's *Transpose > Cells across columns into rows...* function on columns and the *Fill down* operation are particularly handy for this.

* **Numbers and units:** For numeric columns, try to remove any currency specifications and non-decimal separators, such as commas for thousands steps (NNN,NNN.NN). All dates imported into OpenSpending must be of the form NNNN.NN, additional commas or spaces should be removed. Make sure the unit is a single number and not shortened by thousands or millions.

* **Text & Encoding:** In text columns, remove any surrounding spaces, commas and full stops. Get rid of prefixes that are common to all values of the column. When importing text with non-English characters, make sure to save your data with the UTF-8 character encoding. If umlauts or other diacritica do not show up correctly you might have to try converting the input data to UTF-8 from another encoding. OpenSpending currently does not support LTR languages and CJK text.

* **ISO Dates:** OpenSpending only accepts dates in a single form, YEAR-MM-DD. You may have to convert other representations (such as spelled out month names, or other orderings of the information) into this format. An easy way to do this may be splitting the date into several columns and then merging the columns in the desired order. Take special care to distinguish between the US and conventional styles of writing dates: MM/DD/YEAR (US) vs. DD/MM/YEAR (rest of planet). Beware of the date handling methods used in Excel, it is often better to simply set date columns to be interpreted as text.

* **Excel Macros & Protection:** For source data in Excel files, make sure that all macros in the document were correctly turned into static values by the CSV exporter function. If your Excel sheet has export protection, you may need to find an appropriate cracking tool.

* **Entity names:** Google Refine offers a very convenient reconciliation API that can be used to convert the names of such entities as countries, companies or people listed on Wikipedia into a canonical spelling. Take care to set a match score threshold that does not risk too many false positives.

* **Column names:** While this is not necessarily a problem in OpenSpending, some programs may stumble if your column names contain characters like spaces, slashes, quotes, percentage signs etc. Be safe and use conservative_column_names or CamelCasedNames.

* **Consider privacy:** Remove unnecessary personal information such as telephone numbers or social security identifiers for individuals as well as information about third parties that may be in your source data.

### What is too much cleansing?

There is a tension between two goals you may have in presenting the data: to show the data as-is, with little or no cleansing applied (i.e. to highlight both the content and the form in which it is  released) and to maximise the information and utility for the user. 

OpenSpending advocates a moderate level of cleansing: remove obvious mistakes but don't overdo processing and oversimplify the structure in the process - you may end up inadvertently removing relevant information.

### Share the footprints

The key quality criterion of data cleansing is how well you document what you are doing. This should include both a human readable account of the cleansing you have performed and any scripts, databases or intermediate data dumps you produce while working with the data. Don't let the fact that what you have done may be a bit murky become an excuse for not publishing such information - it is the very reason you should.


