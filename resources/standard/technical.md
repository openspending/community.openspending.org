---
layout: standard
title: Technical Specification
---

<div class="alert">
    This document is intended as a basis for discussion, the depth of the specification
    does not yet allow for an implementation. 
</div>

The primary goal of this specification is to be **useful**: we want to offer a format that can 
be easily generated from commonly-used financial management systems and, most of all, a format 
that helps by end-users - whether they are tech-literate developers or data journalists whose
skills may be very limited.

A good example for a **pragmatic specification** is the [General Transit Feed Specification](https://developers.google.com/transit/gtfs/reference) by Google, which is widely used to share timetable and route information between public transport providers and data re-users (originally Google Maps).

<h3>What are the components of the technical specification?</h3>

The specification will contain two parts: the **core specification** and additional **modules**. The core will include instructions on the packaging of spending datasets to combine data and metadata, a minimal set of required metadata attributes and a modeling system in which modules can be expressed. The modules themselves will specify and document well-known DSPL concept which can then be re-used across different datasets.

<h3>What file formats are used?</h3>

The format will be **[Comma Separated Values (CSV)](http://tools.ietf.org/html/rfc4180) for the data and [JavaScript Object Notation (JSON)](http://json.org/) for metadata**. The deciding argument for CSV is its universal tool support, both for export from all major databases and import into common tools, such as spreadsheet applications. Data and metadata documents will be **combined into a Zipfile container**.

Other technologies, such as XML or Linked Data (RDF) are less appropriate for the representation of bulk transactional data, require explicit exports and conversion while offering less tool support. RDF in particular offers great joys in modeling but has seen few production users.

<h3>How is metadata represented?</h3>

We're planning to use a [simplified form](https://github.com/nickstenning/dspljson) of Google's [Dataset Publishing Language (DSPL)](https://developers.google.com/public-data/) which contains both generic dataset metadata (title, publisher, URL) and a logical data model to describe to contents of the associated CSV files, such as reference files and fact tables. 

<h3>Open Issues</h3>

* **Currency conversion**: do we want to specify a base currency (e.g. 2000 US Dollars or SDR) in which fact table data will be provided?
* **Mandatory metrics and dimensions**: do we want to mandate the presence of at least one related pair of a currency metric and a time dimension?
