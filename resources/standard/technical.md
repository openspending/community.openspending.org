---
layout: standard
title: Technical Specification
---

The primary goal of this specification is to be **useful**: we want to offer a format that can 
be easily generated from commonly-used financial management systems and, most of all, a format 
that helps by end-users - whether they are tech-literate developers or data journalists whose
skills may be very limited.

A good example for a **pragmatic specification** is the [General Transit Feed Specification](https://developers.google.com/transit/gtfs/reference) by Google, which is widely used to share timetable and route information between public transport providers and data re-users (originally Google Maps).

<h3>What file format is used?</h3>

The format will be [Comma Separated Values (CSV)](http://tools.ietf.org/html/rfc4180) for the data and [JavaScript Object Notation (JSON)](http://json.org/) for metadata. The deciding argument for CSV is its universal tool support, both for export from all major databases and import into common tools, such as spreadsheet applications. Data and metadata documents can be combined into a Zipfile container.

Other technologies, such as XML or Linked Data (RDF) are less appropriate for the representation of bulk transactional data, require explicit exports and conversion while offering less tool support. RDF in particular offers great joys in modeling but has seen few production users.

