---
lead: true
title: Get Involved
authors:
- Anders Pedersen
redirect_from:
- /contribute/
---

Glad to see you here! 

This site is for enthusiastic doers, citizens and budget nerds from
across the world. We care deeply about welcoming everyone regardless
of skills and will do what we can to help you getting started!

## Connect with the Community

There's lots of general and technical discussion happening on our
[OpenSpending Forums](https://discuss.okfn.org/c/openspending/none)
(also in
[Portuguese](https://discuss.okfn.org/c/openspending/gastos-abertos)!).
We also have an IRC channel on Freenode:
[#openspending](http://webchat.freenode.net/?channels=openspending).
For the full list of ways to get in touch, visit our
[contact][contact] page.

[contact]: {{site.baseurl}}/about/contact/

## Contribute to the Fiscal Data Package Spec

We're hard at work on defining
[Fiscal Data Package](http://fiscal.dataprotocols.org/), a simple,
open technical specification for describing government budget and
spending data.

We welcome input from the community regarding the specification. You
can contribute to the development process by leaving suggestions and
queries in the
[issue tracker](https://github.com/openspending/fiscal-data-package/issues).

## Contribute to the Development of OpenSpending Next

[OpenSpending Next](/next/) is the next generation of the OpenSpending
platform.  We are now creating a "minimum viable product" version.

## Upload and Package Your Data

Contribute fiscal data sources to our
[registry tracker](https://github.com/os-data/registry/issues).  The process is simple:

* [Open a new issue](https://github.com/os-data/registry/issues/new?title=Dataset&body=Link:%0ADescription:)
* Write a brief description of the data and how to interpret it
* Provide a link to the data (hosted as flat files (e.g. CSV or XLSX) on GitHub would be best, if possible)

This will allow us to look at the data and see how well it fits with our
current assumptions. We can then work together on steps to get the
data imported into the flat file DataStore.

## Code

* [Fiscal Data Package](https://github.com/openspending/fiscal-data-package) (FDP): A standard for publishing fiscal data
* [Fiscal Data Package (schema)](https://github.com/dataprotocols/schemas/blob/master/fiscal-data-package.json): JSON Schema for validating a Fiscal Data Package
* [Fiscal Data Packager](https://github.com/openspending/fiscal-data-packager): A simple app to create a FDP from CSV
* [Fiscal Data JS](https://github.com/openspending/fiscal-data-js): A data access library to create "views" on fiscal data (e.g. for visualization)
* [Fiscal Data Package Viewer](https://github.com/openspending/fiscal-data-package-viewer): A single app to visualise data in common formats (e.g. treemap, table)
* [Datastore CLI](https://github.com/openspending/os-datastore-cli): A commandline interface/python library to push FDP directly to the OpenSpending flat file datastore
* [OS Authz](https://github.com/openspending/os-authz-service): A service that provides access to different OpenSpending services
* [Cosmopolitan](https://github.com/openspending/cosmopolitan): An API server for country data
* [Babbage](https://github.com/spendb/babbage): A lightweight OLAP engine
* [Cubepress](https://github.com/openspending/cubepress): A flat file aggregator using Babbage
* [community.openspending.org](https://github.com/openspending/community.openspending.org): This website
