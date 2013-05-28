---
title: "Case Study: Texty"
layout: osi
---

# Texty, Ukraine

Project: [z.Texty.ua](http://z.texty.org.ua/) - procurement database
based on data from the Ukrainian government.

Texty.ua was established in 2010 as an NGO by Anatoliy Bondarenko and
Roman Kulchynsky (Editor in chief). They both have a background inside
Ukrainian media outlets - Roman as Editor in Chief at the Ukrainian
weekly, Tyzhden. Anatoliy has served as an editor and programmer with
scientific educational background.

Topics: Texty decided to pursue procurements, as this proved to be the
best possible way to cover public spending, due to the fact that
transactional spending is not available. The result z.texty.org.ua, a
searchable database for public procurements was completed in the spring
of 2012. The database is updated weekly and contains procurement data
since 2008.

State and local budgets also remain as priorities for Texty, though they
do not currently have resources to conduct analysis more frequently than
once a year. The state budget process in Ukraine is described as complex
and difficult to follow. So site is currently monitoring these changes
to the budget. Texty would like to play a role in this.

## Tools

Mapping the Tools: Texty work on budget and procurement data with a
variety of tools.

Open Refine: When working with raw data

R: For analysis of data. They do not point to specific needs for tools,
but highlight that R is not always a user friendly tool for data
analysis.

d3.js: For visualizing them online.

Model: Texty sustains its activities by providing data analysis and
visualisations for both CSOs and media outlets.
They [delivered data
analysis](http://forbes.ua/ratings/people) for Forbes Ukraine, on
concentration in procurement contracts within the business elite.

Challenges: Texty points to the lack of resources in the data journalism
field as the biggest challenge. While both data and tools are available,
the lack of resources for completing the required data analysis
currently hinders more elaborative projects on spending transparency.
While CSOs and media outlets regularly source data investigations with
Texty, the demand is currently not enough for taking advantage of the
data actually available. Texty is supplementing their investigations
with offering data-journalism trainings.

Open database for public procurements in Ukraine
In 2011 when Texty began working on public procurements in Ukraine.
Getting the data was a top priority because of the huge volumes
available and rumors about big level of corruption in this field. In
2012 spending on procurements was approaching 40% GDP of Ukraine, which
could be one of the highest in the world.

The main problem with the govermental site
[http://tender.me.gov.ua](http://tender.me.gov.ua) is working with the
data. The site requires account and login and only gives access to the
data via a html-table with max 100 results from one of the issues of the
official bulletin about public procurements. No tables are sortable and
no records have been linked between each other. Finally and most
important the data is dirty: you could easily find several different
versions of the same supplier (company) name. The site includes around
5-10 thousand tenders per week.

Getting data from the site

The Texty team wrote a ruby script to mimic user login, check for
updates and to scrape data from html webpages, all of which had a
different structure. After cleaning they imported it into a relational
database as normalised data, for example creating links between records
for each participant. The database is updated approximately twice per
week.

The tool stack:

1.  [nginx](http://wiki.nginx.org/Main)
2.  [sinatra](http://www.sinatrarb.com/)
3.  [mysql](http://www.mysql.com/)
4.  and a novel approach for user interface based on javascript library
    called [Tangle.js](http://worrydream.com/Tangle/).

From the main page it is possible to:

1.  explore data about tenders in 'real-time',
2.  change the textual query and immediately get information on the
    total volume for a particular industry, participant or/and period of
    time.

Additionally:

3.  Clicking on total volume yields all tenders therein
4.  For each company participating in a tender the database contains
    information on all other deals which the company has won.
5.  Recently, an "advanced search" page has been added, with the
    possibility to export result in form of a simple and portable CSV
    format.

Impact and coverage


One year into the projects existence, the site reached about 1,500 daily
users per day despite having almost zero advertising. It has gained
attention and been used by investigative journalists as well. Some
stories were published in the biggest independent
internet outlet - Ukrainian Pravda (approx 200,000 readers per day).

In autumn 2012 a joint project with Forbes.ua called "Champions of
tenders" was launched.

The Texty team shared the open part of their data, information about
deals (including name of firm and volume of money) from their database
through a simple web API. Next, the team from Forbes.ua used them in
their database to link firms to names of owners (Forbes.ua mantains a
proprietary database of these). The Texty team also made an interactive
visualization of this data for Forbes.ua
(http://forbes.ua/ratings/people).

![](http://placehold.it/500x500&text=Forbes.ua)

The impact of open tender data

Since 2008 when information about tenders became openly available for
the first time, there has been a shift in the public opinion about
tenders and public spending on procurement. Today there seems to be a
real awareness about corruption in procurements, though still not a
clear idea about the actual scale of the problem. For example, there is
even a TV-programme on the channel TVi, opposing the government called -
"Tenders News".

Ukraine has a couple of projects about tenders, though Texty appears to
be the most sizeable and complete database.

There has however been continuing lobby attempts to close down access to
as much information about tenders as possible and many of these have
unfortunately been successful. Last example was a law accepted by
majority in Ukrainian parliament in autumn 2012, which meant that 35% of
all volumes of tenders would be hidden from the public.

The ongoing hope for transparency in public procurement is based on a
proposed agreement about association between Ukraine and the EU, which
includes requirements about transparency in tenders.
