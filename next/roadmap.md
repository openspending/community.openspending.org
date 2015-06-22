---
layout: page
section: next
title: 2015 Roadmap
---

## Overview

A roadmap for developing a minimal viable product (MVP) of the next OpenSpending platform. This does not mean that the new platform will be ready to *replace* the current OpenSpending. Rather, it should be a usable product that provides some user value, and demonstrates the utility of both the microservices architecture, and the flat file Datastore.

**The components for this MVP are described in this diagram:**

<img src="/img/osnext-mvp.png" />

**The MVP is the first step on the path to the full architecture as described in [OSEP-01](http://labs.openspending.org/osep/osep-01.html):**

<div style="text-align: center"><img width="60%" src="http://labs.openspending.org/osep/img/01-tech-overview-subcomponents.png" /></div>

## Goals

* Provide a simple flow for a user to start with a file of spend data and have it visualized in a few of steps
* Provide basic validation of the concepts in OSEP-01
* Provide a good testing ground for iterating on OpenSpending Data Package
* Provide a migration path for all existing data in openspending.org to the new Datastore

## Supported user flows

The MVP must be able to address these user flows.

### Upload spend data

1. User has a file of spend data
2. User interacts with a web interface to get this data modeled into an OpenSpending Data Package
3. User uploads her data/package to the OpenSpending Datastore
4. User can download the data/package from the OpenSpending Datastore

### View a spend data visualization

1. User can see a list of data packages that are on OpenSpending
2. User can navigate to a high-level visualisation of the data in a given data package

## Timeline

**June 2015 - December 2015**

We are setting out an MVP that we hope to be able to deliver over the next ~6 months. This is obviously highly dependant on time and resources, and so is just an intention, and not a requirement.

Some work needs to be executed in sequence (more or less), and some can occur in parallel.

### Core work, in sequence

* **Datastore:** A correctly configured object storage backend for OpenSpending Data Packages.
* **Data load:** A service that allows a user to model and load data, and save that data to the datastore.
* **Static aggregation:** A service that provides high-level aggregation over the Data Packages in the datastore.
* **Visualization:** A set of simple, high-level visualizations using the computed static aggregations in the datastore.
* **Index/Registry:** A service that provides the main entry point to OpenSpending, allowing users to navigate a list of existing Data Packages, see information on a specific Data Package, and interact with simple visualizations for a Data Package.

### Parallel work

* **Auth/z service:** Users can authenticate, and be authorized to perform actions
* **Service integration:** Different services can communicate
* **Open Spending Data Package:** User data can be modeled and packaged with useful information about it
* **Data migration:** Existing data on Open Spending can move to a new home
* **Documentation:** high-level documentation for the new system

In the **Components and teams** section below, work is broken down into components that would ideally be managed by a team.

## Components and teams

The new architecture proposes a collection of interacting services. This helps us break down work into components that would ideally be managed by a team.

Each team should:

* Work to a set of user stories and basic specs that have been agreed on with other teams
* Regularly sync with other teams
* Generally organize their own work

Teams could consist of one person. The same team might move on through multiple components.

Approximate estimates of time are given below. This is just to get a rough understanding of the scope of the work.

### Datastore team

* Component: Datastore
* Status: *required*
* Team: N/A (@pwalsh responsible)
* Estimate: 1 day

Requires minimal work (just correct configuration of S3). Does not require a team.

### Data load team

* Component: Data modeler and loader
* Status: *required*
* Team: @pwalsh
* Estimate: 10 days
* Requires: Accepted OSEP-04 in order to deliver
* [Specifications](02-dataload.html)
* **Interested?: [Join the team]({{ site.issues_url }}/1)**

A service that provides both a commandline and Web UI for loading data into the OpenSpending Datastore.

The Web UI is more important. We want to provide an excellent 1-2-3 type user experience for loading data into OpenSpending.

This service expects well-formed data sources, and can either accept data packages that are already modeled (ie: already have a `datapackage.json` descriptor which is a valid Open Spending Data Package), or, perform the modeling of the data with user interaction.

Some initial ideas for this on the command line have been explored in [OSCLI-POC](https://github.com/openspending/oscli-poc).

### Static aggregation team

* Component: aggregation over flat files
* Status: *required*
* Team: @pwalsh @rgrp
* Estimate: 5 - 10 days
* Requires: Accepted OSEP-04 in order to deliver
* [Specifications](03-static-aggregation.html)
* **Interested?: [Join the team]({{ site.issues_url }}/2)**

A job that runs when a data package is uploaded to generate aggregated spend reports from the data. We'd have to define what the scope of aggregations is, and also consider the feasibly of this method of aggregation with data we expect in Open Spending.

Some initial work in this direction has been explored in [cubepress](https://github.com/openspending/cubepress).

### Visualisation team

* Component: data visualizations over aggregated spend data
* Status: *required*
* Team: None
* Estimate: 10 days
* [Specifications](04-visualisation.html)
* **Interested?: [Join the team]({{ site.issues_url }}/3)**

Maybe it is time to retire [openspendingjs](https://github.com/openspending/openspendingjs), or refactor. In any event, we'd want to provide at least one high-level data visualization using the aggregated data files.

### Index/Registry team

* Component: Index/Registry of Data Packages
* Status: *required*
* Team: None
* Estimate: 2 days
* [Specifications](05-index-registry.html)
* **Interested?: [Join the team]({{ site.issues_url }}/4)**

A simple flask app that:

* Provides the front page of the project
* Provides a list of the currently available data packages on the datastore
* For each Data Package in the list, provides:
    * a link to the `datapackage.json`
    * a link to a high-level visualization of the spend data therein (eg: Treemap)

### Auth/z team

* Component: Auth service
* Status: *recommended*
* Team: None
* Estimate: 7 days?
* [Specifications](06-auth.html)
* **Interested?: [Join the team]({{ site.issues_url }}/5)**

**Note**: Marked here as *recommended* as it is possible that we would mock this out, but it would mean that our MVP is not publicly usable.

We need a service to authenticate users, and authorize user actions. It is likely that Open Knowledge would like to hosted an authentication service that could be used on many Open Knowledge web properties. So, work on this may end up being more directly for Open Knowledge, than for Open Spending. To be discussed.

The minimum auth/z requirements we have for this MVP are:

* Authenticate a user
* Authorize and authenticated user to upload files to the Open Spending Datastore.

### Service integration team

* Component: pub/sub or similar service
* Status: *nice to have*
* Team: @tryggvib
* Estimate: ?
* [Specifications](07-integration.html)
* **Interested?: [Join the team]({{ site.issues_url }}/6)**

In general, Open Spending will need some type of tasks service (pub/sub, etc.) to have interaction between different services. Even here in the scope of the MVP, we have events/actions that could leverage tasks (eg: on upload of a data package, register an aggregation task). We can get away without it now, but it may be better to design with this from the beginning.

### OpenSpending Data Package team

* Component: Specification
* Status: *required*
* Team: @rgrp @pwalsh @tryggvib
* Estimate: ongoing, as part of other work
* **Interested?: [Join the team]({{ site.issues_url }}/7)**

We'll accept OSEP-04 at a state in which we can start working with it, but expect to iterate on details continuously.

### Data migration team

* Component: migration scripts
* Status: *recommended*
* Team: @rgrp
* Estimate: ? 2 - 3 days ?
* [Specifications](08-data-migration.html)
* **Interested?: [Join the team]({{ site.issues_url }}/8)**

### Documentation team

* Component: Documentaion
* Status: *recommended*
* Team: @tryggvib
* Estimate: *ongoing*
* **Interested?: [Join the team]({{ site.issues_url }}/11)**

A team responsible for making sure services are documented and collecting them into a single page. Especially important for overview docs.
