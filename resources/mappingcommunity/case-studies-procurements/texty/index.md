---
layout: page
status: publish
published: true
title: Texty
author:
  display_name: Neil Ashton
  login: nmashton
  email: neil.ashton@okfn.org
  url: ''
author_login: nmashton
author_email: neil.ashton@okfn.org
wordpress_id: 1163
wordpress_url: http://blog.openspending.org/?page_id=1163
date: '2013-09-03 17:51:26 +0700'
date_gmt: '2013-09-03 17:51:26 +0700'
---
<div class="well">Project: <a href="http://z.texty.org.ua/">z.texty.org.ua</a>, a procurement database based on data from the Ukrainian government.</div>
<p>Texty.ua was established in 2010 as an NGO by Anatoliy Bondarenko and<br />
Roman Kulchynsky (Editor in chief). They both have a background inside<br />
Ukrainian media outlets, Roman as Editor in Chief at the Ukrainian<br />
weekly, Tyzhden. Anatoliy has served as an editor and programmer with<br />
a scientific educational background.</p>
<p>Texty decided to pursue procurements, as this proved to be the<br />
best possible way to cover public spending due to the fact that<br />
transactional spending is not available. The result was <a href="http://z.texty.org.ua/">z.texty.org.ua</a>, a<br />
searchable database for public procurements completed in the spring<br />
of 2012. The database is updated weekly and contains procurement data<br />
from 2008 onwards.</p>
<p>State and local budgets also remain priorities for Texty, though they<br />
do not currently have the resources to conduct analysis more frequently than<br />
once a year. The state budget process in Ukraine is complex<br />
and difficult to follow, so the site is currently monitoring changes<br />
to the budget, and Texty would like to play a role in this.</p>
<p>## Tools</p>
<p>Texty work on budget and procurement data with a variety of tools.</p>
<p>* Open Refine: working with raw data</p>
<p>* R: analysis of data</p>
<p>* D3.js: online data visualization</p>
<p>## Model</p>
<p>Texty sustains its activities by providing data analysis and<br />
visualisations for both CSOs and media outlets.<br />
They delivered [data<br />
analysis for Forbes Ukraine](http://forbes.ua/ratings/people) concerning<br />
concentration in procurement contracts within the business elite.</p>
<p>## Challenges </p>
<p>Texty points to the lack of resources in the data journalism<br />
field as the biggest challenge. While both data and tools are available,<br />
the lack of resources for completing the required data analysis<br />
currently hinders more elaborate projects on spending transparency.<br />
While CSOs and media outlets regularly source data investigations with<br />
Texty, the demand is currently not enough for taking advantage of the<br />
data actually available. Texty is supplementing their investigations<br />
with offering data-journalism trainings.</p>
<p>### Open database for public procurements in Ukraine<br />
In 2011, when Texty began working on public procurements in Ukraine,<br />
getting the data was a top priority because of the huge volumes<br />
available and rumors about massive corruption in the field. In<br />
2012, spending on procurements was approaching 40% of the GDP of Ukraine, which<br />
could be one of the highest in the world.</p>
<p>### Problems with the govermental site</p>
<p>[http://tender.me.gov.ua](http://tender.me.gov.ua), the source of procurement data, presents several issues. It requires an account and login, and it only gives access to the<br />
data via an HTML table with max 100 results from one of the issues of the<br />
official bulletin about public procurements. No tables are sortable, and<br />
no records have been linked to one other. Finally and most<br />
importantly, the data is dirty; you can, for example, easily find several different<br />
versions of the same supplier (company) name.</p>
<p>## Getting data from the government site</p>
<p>The Texty team wrote a Ruby script to mimic user login, check for<br />
updates, and to scrape data from HTML webpages, all of which had a<br />
different structure. After cleaning, they imported the data into a relational<br />
database as normalised data, for example creating links between records<br />
for each participant. The database is updated approximately twice per<br />
week.</p>
<p>The tool stack:</p>
<p>*  [nginx](http://wiki.nginx.org/Main)<br />
*  [sinatra](http://www.sinatrarb.com/)<br />
*  [mysql](http://www.mysql.com/)<br />
*  [Tangle.js](http://worrydream.com/Tangle/) (for a novel approach to the user interface)</p>
<p>## Features</p>
<p>From the main page, it is possible to explore data about tenders in realtime and to change the textual query and immediately get information on the total volume for a particular industry, participant, and/or period of time.</p>
<p>Additionally, clicking on total volume yields all tenders therein. For each company participating in a tender, the database contains information on all other deals which the company has won. Recently, an "advanced search" page has been added, with the possibility to export result in form of a simple and portable CSV format</p>
<p>## Impact and coverage of the project</p>
<p>One year into the project's existence, the site reached about 1,500 daily<br />
users per day, despite having almost zero advertising. It has gained<br />
attention and been used by investigative journalists as well. Some<br />
stories were published in the biggest independent<br />
internet outlet, Ukrainian Pravda, which has approximately 200,000 readers per day.</p>
<p>In Autumn 2012, a joint project with Forbes.ua called "Champions of<br />
tenders" was launched. The Texty team shared the open part of their data, information about<br />
deals from their database (including the names of firms and volumes of money),<br />
through a simple web API. Next, the team from Forbes.ua used the data in<br />
their database to link firms to names of owners—Forbes.ua mantains a<br />
proprietary database of these. The Texty team also made an [interactive<br />
visualization of this data](http://forbes.ua/ratings/people) for Forbes.ua.</p>
<p><a href="http://www.flickr.com/photos/94746900@N06/8895650387/" title="thumbnail by anderspedersenOKF, on Flickr"><img src="https://farm9.staticflickr.com/8123/8895650387_c1f6582979_o.jpg" width="600" height="373" alt="thumbnail"></a></p>
<p>## Impact of open tender data</p>
<p>Since 2008, when information about tenders became openly available for<br />
the first time, there has been a shift in public opinion about<br />
tenders and public spending on procurement. Today there seems to be a<br />
real awareness about corruption in procurements, though still not a<br />
clear idea about the actual scale of the problem. For example, there is<br />
even a TV-programme on the channel TVi, opposing the government, called<br />
"Tenders News".</p>
<p>Ukraine has a couple of projects about tenders, though Texty appears to<br />
be the most sizeable and complete database. There has, however, been continuing lobby attempts to close down access to<br />
as much information about tenders as possible, and many of these have<br />
unfortunately been successful. The most recent example was a law accepted by a<br />
majority of the Ukrainian parliament in Autumn 2012, which meant that 35% of<br />
all volumes of tenders would be hidden from the public.</p>
<p>The ongoing hope for transparency in public procurement is based on a<br />
proposed agreement about association between Ukraine and the EU, which<br />
includes requirements about transparency in tenders.</p>
<p>**Next**: [OpenTED, Opening Tender Electronic Daily](http://community.openspending.org/?page_id=1165)</p>
<p>**Up**: [Case Studies: Procurements](http://community.openspending.org/?page_id=1159)</p>
