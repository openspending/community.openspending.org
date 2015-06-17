---
layout: page
status: publish
published: true
title: Hutspace
author:
  display_name: Neil Ashton
  login: nmashton
  email: neil.ashton@okfn.org
  url: ''
author_login: nmashton
author_email: neil.ashton@okfn.org
wordpress_id: 1161
wordpress_url: http://blog.openspending.org/?page_id=1161
date: '2013-09-03 17:50:17 +0700'
date_gmt: '2013-09-03 17:50:17 +0700'
---
<div class="well">Project: scraping, analysing and publishing procurement data. In progress, with version 1.0 scheduled for publication June, 2013.</div>
<p><em>This chapter is based on an interview with Emmanuel Okyere, Hutspace (Ghana).</em></p>
<p>Emmanuel Okyere is running a project to scrape, publish, and<br />
analyse the Ghana procurement register, while working on his own<br />
IT startup.</p>
<p>Emmanuel has built a database of contract awards for Ghana using Python<br />
scrapers and parsers, [Celery](http://www.celeryproject.org), and PostgresSQL. The<br />
preliminary result shows 4000 contract awards and 2000 current<br />
procurement opportunities. Future plans include building a searchable<br />
database and a flat CSV file download option in order to enable<br />
journalists and CSOs to work with the data.</p>
<p>## Technical challenges</p>
<p>### Cleaning data</p>
<p>> “Cleaning the data has been a substantial issue for the<br />
> project. There’s a lot of validation, which we need to do before we can<br />
> publish it simply because the data appear to be inaccurate. As an<br />
> example, we might have unrealistically small amounts appearing in a<br />
> contract award, or a date might not make sense. This has been the most<br />
> substantial bottleneck for the project.”</p>
<p>### Reconciling company entities</p>
<p>> “Many companies appear with a variety of<br />
> entities, and so finding a good way to reconcile companies which are<br />
> actually the same has been difficult.”</p>
<p>Emmanuel is planning to utilize a helpful codebase from the open<br />
parliament field, originally developed by MySociety for name<br />
reconciliation of parliament members, for reconciling the company<br />
entities.</p>
<p>### Identifying the correct amounts</p>
<p>A surprising problem in the procurement<br />
data has turned out to be the varying currency denominations appearing,<br />
such as GBP and USD. Finding appropriate historical exchange rates and<br />
calculating these has been cumbersome, but it is important in<br />
order to make the data as accessible as possible.</p>
<p>## Community challenges</p>
<p>Emmanuel points out that both the lack of knowledge about the<br />
availability of procurement data as well as the lack of skills to<br />
analyse it among journalists and CSOs are the main barriers for<br />
achieving more usage of the data.</p>
<p>> “For much of the work to be done on the data, having skills to use Excel<br />
> would actually be sufficient for journalists in order to get to work<br />
> with the data. However, skills to use Excel for analysis are lacking<br />
> among almost all journalists today. When it comes to more challenging<br />
> tasks which require coding skills for analysing the data, I know<br />
> actually only one journalist. She will be involved in this project.</p>
<p>> “Trainings could help equip more journalists to work with the<br />
> procurement data we are planning to release. We really need more people<br />
> to look and use the data, but that require that they have the skills. I<br />
> think that is what trainings like data bootcamps are for.</p>
<p>> “As publishers of the database, we would like to build visualisations to<br />
> spot trends in the data. For instance, we have noticed that when new<br />
> governments get into power, we see this reflected in the procurement<br />
> data as new contractors appear while others vanish. This is analytical<br />
> work we can do which I think journalists will not be able to do on<br />
> their own.”</p>
<p>**Next**: [Texty](http://community.openspending.org/?page_id=1163)</p>
<p>**Up**: [Case Studies: Procurements](http://community.openspending.org/?page_id=1159)</p>
