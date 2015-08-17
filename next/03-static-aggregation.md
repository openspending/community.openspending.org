---
layout: docs
section: next
type: spec
title: Static aggregation
---

## Overview

<img src="https://docs.google.com/drawings/d/1rHcMd5hRHwxGYjeFoHlHn8sqqLXSDClhNV2eRrAwYAg/pub?w=960&amp;h=720">

OpenSpending users expect to be able to do something more than *just structure and store* their data with OpenSpending. Part drive behind the new architecture is to allow 3rd parties to easily hook in to the platform at different points and provide "more". In any event, there are some core functionalities that any user should expect to be able to use immediately on loading data into the system, such as high-level visualisations.

If we posit high-level visualisations as an initial goal for providing value beyond the core proposition of structure and storage, then we need a service to power these visualisations with aggregation sover the raw data.

Aggregation is a deep problem to solve. We certainly expect to offer a rich API for querying data from an OLAP data store or similar. However, for a great many use cases of spend data, simple aggregations over dimensions like time and category will suffice. These aggregations can power treemaps, pie charts, and even simple tabular views that expose the core stories that a given dataset tells.

In order to acheive this high-level aggregation, we will provide a simple service that creates flat file aggregations for each Data Package added to the system, served directly from the file storage with no additonal moving parts required.

## Use cases

* High-level aggregate data to power basic visualisations, such as treemaps
* The basic math of a large dataset - e.g: sum per category, sum per year, and so on

## User stories

* As a user, I want aggregated representations of my data created for me automatically, so that I can access a high-level view of the data I have added to OpenSpending

## Implementation

Start with [cubepress](https://github.com/openspending/cubepress), providing a service around it that first reads metadata out of a Data Package, and then feeds in files and scopes for aggregation.
