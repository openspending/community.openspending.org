---
title: "Appendix: Putting the Open Data Into Open Budgets"
layout: osi
---

# Putting the Open Data Into Open Budgets

We have looked in detail in this report at criteria which make it difficult for organisations to use data that has been released by governments.  In January 2013, we hosted a community call with the International Budget Partnership to look at what the demands of the Open Data Community are with regard to Open Budgets. Despite both featuring the word “Open” - there is still a disconnect between the use of “open” to signify availability and “open” to signify absence of legal, technical and social restrictions. 

The purpose of the call was to investigate whether it would be possible to specify the demands of the Open Data Community with relation to budget and spending data. The notes below are paraphrases of the conversation, and together with the following sections will hopefully provide some clear guidelines to liberate budget and spending data.  

## Questions

#### How should updates and changes to budget data be documented or tracked? One requirement could be to ask governments to clearly specify for all the posted documents the "when" (writing something like  "latest  updated on"  or "posted on", etc...)

The open data community is quite familiar with version numbers, so using them is one possible solution. 
Crucial is that there should be access to all drafts (i.e. they should not be removed from their place of publication and should remain available) even when new versions are published. 

#### How should budgetary breakdowns and classifications be outlined?

The conclusion from the group was that this was largely a political question and the answer would depend on context. There may be far more specific requests for breakdowns than this, we highlight here only the simplest of requests. Nevertheless - it is possible to infer some preferences from the broader context of the interviews from this report: 

* The most popular request from our group was for functional or programme classifications. (It is common to receive data in administrative breakdowns and then have to convert it, e.g. in order to visualise it to explain to citizens where their money goes.)
* It should be possible to map the (functional) classifications from the budget formulation process onto the spending categories to see projected vs. actual expenditure. 

#### For how long should budget information be kept online (minimum amount of time)?

The participants of the call felt quite strongly that as the costs of storing information online were so minimal, this question was essentially redundant (i.e. the answer was "forever"). 

LC - I would add that for a compromise measure, if a government feels it is absolutely necessary to remove data after a certain period of time (this should be a minimum of several years after original publication, longer if the period to which the budget relates is greater than a year), they should specify at time of publication, clearly the time and date on which the information will be removed. This will allow civil society organisations sufficient time to make a backup copy for themselves. 

In this last case, we would however urge governments to consider a variety of arguments for why this data should not be removed from the site: 
<ul><li><strong>Reason number 1:</strong> Provenance is King. In order for Civil Society Organisations to be able to do their work in a reliable and evidence-based manner, they need to be able to refer to the original canonical dataset and provide a paper trail which shows any changes made to the original data for the purposes of cleaning or analysis. In the case where data is present online, the simplest solution is to provide a URL to reference the original source of the data in any analysis or presentation of evidence. If the original data disappears, then neither the government, nor the civil society organisation can trace back the steps to ensure that all conclusions are correct. Many investigations require historic data. </li>
* <li><strong>Reason number 2:</strong> Governments also require access to the historic data for their own analysis. Publishing it online can eliminate lag times between departments and hence improve efficiency of the government itself. See this <a href="http://openspending.org/resources/gift/chapter2-2.html">case study</a> for more details. </li> <p>
* <li><strong>Reason number 3:</strong> There is a good reason for information to be stored as digital information - often it is safer. Paper documents for example are at <a href="http://www.google.com/url?q=http%3A%2F%2Farticles.timesofindia.indiatimes.com%2F2012-06-23%2Findia%2F32381434_1_fire-department-mantralaya-data-centre&sa=D&sntz=1&usg=AFQjCNGXnWD5ZJnHPdbq2goWL1XWfCQvVQ">risk of fire</a>, water damage and loss, having a digital backup is crucial to ensure access for all, including government officials. </li> 
</ul>

**It should also be possible to download all of the budget information* *in bulk*. Preventing bulk downloads by using systems such as CAPTCHA is not acceptable. 

Some interviewed requested data to be released via an API. This is indeed a useful move particularly when data is updated regularly, but should not be the only method to aquire the data - many non-technical users require simply bulk download of the data. 

#### How should the budget information be displayed in order for interested parties to know where to find it (relatedly if it moves web addresses, links should be provided so users can easily navigate to the new address)?

Ideally - the data would have a constant URL, but in the worst case scenario - the redirects should be clear. 

#### What data formats to provide - ie. machine-readable format?

The number one low-hanging fruit which could be solved in order to vastly improve the usability of available budget and spending (plus procurement and other types listed above) information is to make **data machine-readable**. 

<div class="well"><h4>What does Machine-readable mean?: Implementation guidelines from the UK government.</h4>

The UK government have now issued very good clear, <a href="https://www.gov.uk/service-manual/design-and-content/choosing-appropriate-formats.html">plain-language guides</a> for service managers on which data formats are appropriate for publishing data. The US government has also decreed that all data shall be published in machine-readable formats. An extract from the UK service manual from gov.uk is copied below for the convenience of the reader: 
<ul>
<li><quote><strong>“For data, use CSV or a similar ‘structured data’ format (see also JSON and XML). Do not publish structured data in unstructured formats such as PDF</strong></quote>.</li>
<li><quote><strong>If you are regularly publishing data (financial reports, statistical data, etc.) then your users may well wish to process this data programmatically, and it becomes especially important that your data is ‘machine-readable’. PDFs, Word documents and the like are not suitable formats for data publication. In addition, you should consider making your data available through an API if this will simplify your users’ interactions with your publications. [...]</quote></strong> </li>
<li><quote><strong>If you are publishing a written report that contains statistical tables, provide the tables alongside or in addition to your report in suitable data formats.</quote></strong>
</ul>

[...] 

> <h2>Don’t assume your users can read proprietary formats</h2>
> Wherever possible, publish in accessible, patent-free, <a href="https://en.wikipedia.org/wiki/Open_format">open formats</a>, for which software is widely available on a variety of platforms. If publishing in proprietary formats, you should always make a non-proprietary alternative available.
[...] 
> For tabular data, provide CSV or TSV rather than Excel spreadsheets (.xls/.xlsx).

Read the full version of the guidelines <a href="https://www.gov.uk/service-manual/design-and-content/choosing-appropriate-formats.html">here</a>.

</div>

## Why is this so important? 

Civil Society Organisations currently waste a huge amount of time and resources in converting data from non-machine-readable formats into ones that they can use for analysis, visualisations or other projects. Any data project has a data pipeline: 

![Spending Data Pipeline](http://farm9.staticflickr.com/8399/8883957266_d31e9bb404_z.jpg)

and typically, in the projects we have analysed in this report, finding data, getting data (including extracting data out of formats such as PDFs into usable formats) are the most time intensive part of all of the projects. Extracting data out of non-machine readable formats: 

* **is a waste of time and resources for all involved**. In an ideal world, re-users of the data should be able to dedicate the majority of their time to analysis, presentation and action around the data. It can take weeks or months for organisations to extract all the information from one document or file, enough to make a visualisation or simple analysis. 
* **introduces transcription errors during conversion**. Even current software to extract information from PDFs automatically and can introduce errors. 