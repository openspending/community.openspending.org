---
layout: docs
section: next
type: spec
title: Data load
---

## Overview

<img src="https://docs.google.com/drawings/d/1G7lgAucYCfVM_EtF50Lr43kyOX4Uyg1Er-P0nMTo5u8/pub?w=960&amp;h=720" />

OpenSpending users need to be able to load data into the system. Data loading can be done by one of three methods:

* Web UI
* Web API
* CLI

The main focus right now is on building an excellent Web UI for data loading. The code for the Web UI should use Python libraries in such a way that building a Web API and a CLI will be a trivial extension of the core work.

An initial proof of concept for data loading via CLI has been done: [oscli-poc](https://github.com/openspending/oscli-poc). This code should serve as a starting point for the data load service. At very least, it privides direct demonstration of the steps we require, and the type of services that we need to interact with in order to load data.

## Interface mocks

<img src="/img/dataload_land.jpg">
<div style="text-align: center;"><i>The landing page for the data load service</i></div>
<br /><br />
<img src="/img/dataload_start.jpg" />
<div style="text-align: center;"><i>The user starts by adding files, which are immediately checked for suitability</i></div>
<br /><br />
<img src="/img/dataload_map.jpg">
<div style="text-align: center;"><i>The user then must map the data to the OpenSpending model</i></div>
<br /><br />
<img src="/img/dataload_review.jpg">
<div style="text-align: center;"><i>Before publishing the data, the user checks the mapping and metadata</i></div>
<br /><br />
<img src="/img/dataload_result.jpg">
<div style="text-align: center;"><i>Once the data is loaded, it is processed for basic visualisations</i></div>
<br /><br />

## Use cases

* Model a OpenSpending Data Packages from one or many CSV files.
* Read existing OpenSpending data packages and their associated resources, validate them, and allow the metadata to be further edited.

## User stories

* As a non-technical user, I want to be able to load a CSV file of spend data into OpenSpending, so that I can have it publicly available as part of the OpenSpending database.
* As a non-technical user, I want to be able to load multiple CSV files that make up a single dataset of spend data into OpenSpending, so that I can have it publicly available as part of the OpenSpending database.
* As a non-technical user, I want the data load process to create a "Data Package" from my data for me, so that I do not need to gain any technical understanding of what an OpenSpending Data Package is in order to use OpenSpending.
* As a non-technical user, I want my data files to be automatically checked for basic validity, so that I can be sure that data files I add to OpenSpending meet essential quality requirements.
* As a non-technical user, I want the data load process to do data modeling for me automatically, by taking hints from my field names and data types, so that I do not need to have specialist understand of how the data load process works.
* As a non-technical user, I want the data load process to work with any column headings I may have in my data files, so that I do not have to do any unecessary data preparation in order for OpenSpending to understand my data.
* As a non-technical user, I want the data load process to support cases where I have spend data split over multiple files, so that I do not have to do any unecessary data preparation in order for OpenSpending to understand my data.*
* As a non-technical user, I want the data load process to allow me to add files of data that do not directly contain spend data, so that I have to opportunity to store a complete set of data and access from OpenSpending's datastore, even if some of that data is not directly used in core OpenSpending services, such as treemap visualisations.

## Implementation

### Core libs

#### Validate data structure

* [GoodTables](https://github.com/okfn/goodtables)

#### Validate/infer data > schema

* [GoodTables](https://github.com/okfn/goodtables)
* [JSON Table Schema](https://github.com/okfn/json-table-schema-js)

#### Model data files to a Data Package

* [MakeModel](https://github.com/openspending/oscli-poc/tree/master/oscli/makemodel)

#### Validate data package descriptor

* [CheckModel](https://github.com/openspending/oscli-poc/tree/master/oscli/checkmodel)

#### Validate data package > data

* [CheckData](https://github.com/openspending/oscli-poc/tree/master/oscli/checkdata)

#### Load data package > datastore

* [Upload](https://github.com/openspending/oscli-poc/tree/master/oscli/upload)

#### Create OpenSpending Data Package

* [OpenSpending Data Package](https://github.com/openspending/oscli-poc/tree/master/oscli/osdatapackage)

### Service

#### Web views

* A view to host the JavaScript app

#### Web API

* Endpoints to provide the various load/validate/model functions

### Web UI

#### SPA for load/model interface

* Talks to API from server
* Co-hosted in server (?)
