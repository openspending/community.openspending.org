---
layout: help
title: Loading Data into OpenSpending
---

## Loading Data into OpenSpending

OpenSpending is a flexible platform for storing government financial data. While we 
focus on collecting budget and transaction-level spending data, other types of 
financial reporting, such as accounts or cash flow information, can also be
represented. To accomodate such different types of information, OpenSpending does
not prescribe a specific format for the data that will be reported. Instead, we
enable users to create a custom model for their dataset. 

### Overview

A typical workflow for importing a dataset into OpenSpending will involve the following steps:

* **Gather machine-readable data** from a trustworthy source, collecting metadata 
  such as the source, completeness and time covered in the dataset. 

* **Convert the data** to a denormalized CSV file in which dates and numbers will be 
  [understood by OpenSpending](data-cleansing.html). 

* **Upload the data** to the web, e.g. to [datahub.io](http://datahub.io). 

* **[Create a dataset](/datasets/new) on OpenSpending** and add the address of the dataset as a new
  data source. 

* **Model the dataset** in OpenSpending to assign a logical role to each column in 
  the source table. This includes designating the fields in which time, 
  amount and, optionally, the spender and recipient of a transaction are 
  specified.

* **Load the data** or refine the data based on the feedback given by the
  platform about the data's consistency ([missing or invalid values](data-cleansing.html)). 

After the data has successfully loaded into OpenSpending, you can easily create 
visualizations, run searches or build custom applications on top of the APIs 
provided by the site.


**TODO**: Explain... 

* Facets for search 
* Dataset naming convention 
* Distinguishes capex/current
* Geocoding
* Maps as breakdowns










