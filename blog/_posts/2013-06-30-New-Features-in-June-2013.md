---
layout: post
author: tryggvib
title: New Features in June 2013
published: false
type: post
status: draft
---

![Image by Mosman Library (cc-by 2.0)](https://farm9.staticflickr.com/8205/8206356927_3d5c720658_c.jpg "Badges!")

The summer is here so shouldn't we be outside? Well, in a way we have. You might not have seen much changes to the core OpenSpending platform the last month but we've been hard at work. Bulk of the work this month has been on stuff **outside** of the OpenSpending platform but there have also been some changes to the platform itself.

### Contribution Attribution

First up, and really important to us: **List of Contributors!**

We added a [CONTRIBUTORS file](https://raw.github.com/openspending/openspending/master/CONTRIBUTORS) to the root of the openspending repository, just like you would expect in an open source project like openspending.

If you think your name should be there, we didn't intentionally leave it out. We let *git* list our contributors but unfortunately that's only code contributors, there are plenty of other contributors and we want them in our list as well. Let us know if we missed you in our list and we'll add you!

### Better Documentation

This might seem like a small change, but it's an important one. Our *[installation docs](http://docs.openspending.org/en/latest/install.html)* were slightly wrong, which might have caused our users some problems. They also referred to an outdated version of *solr*.

That's been fixed now so not as much frustration is involved in getting an instance of OpenSpending up and running. If you notice any places in our docs where improvements are needed let us know, or better yet help us by contributiong improvements.

This month we also released some much needed documentation regarding our development process, to help new contributors (and older ones) to know there way around the project organisation. We created a short *[Howto hack on OpenSpending](http://openspending.org/help/hacking.html)* as well as a more detailed documentation about the *[development process](http://openspending.org/help/development-process.html)*. For code reviewers we also documented some *[guidelines for our code review process](http://openspending.org/help/code-review.html)*

### Satellite Template

Our [satellite template](http://github.com/openspending/satellite-template/) exists to make creation of satellite sites easier. This has already been used to create (or initiate) new satellite sites. As always when a fresh piece of software is gets used, unforeseen use cases turn up.

We were notified of those problems and were therefore able to put effort into adapting the satellite template to these new use cases. Some of these changes have been added into the template but as more satellite sites pop up, more changes will get added.

We encourage you to use the satellite site if you are in the process of creating a satellite site, or want to create a satellite site. Let us know if you think we can improve the template.

### Preparations for Inflations

We have been working hard on making it possible to do more accurate historical comparisons with OpenSpending by adjusting for inflation. This is quite a large undertaking but nothing we can't handle. This month we've been laying the foundations for these inflation adjustments.

First we had to collect some data. We decided to start small and start by looking at Consumer Price Indices (CPI). These give a pretty good indication about the inflation and are frequently used in economics. The data was collected and stored in standardised form as a [data package](http://www.dataprotocols.org/) and made available on [http://data.okfn.org/](http://data.okfn.org/data/cpi/).

We went through a lot of CPI data that's available and chose the best open data we could find. If you know of better data we could use, please help us improve the data. Better data results in better inflation adjustments on OpenSpending.

Then we created a small module to read in data packages and called it [datapackage](http://github.com/tryggvib/datapackage). We created a fairly generalised module so that it could reused in other areas of OpenSpending or in other projects. This module, which we implemented in Python and made available in the [Python Package Index](https://pypi.python.org/pypi/datapackage/), almost instantly sparked off an equivalent [module in Java](https://github.com/rossjones/datapackage-java). Then later we received an improvement to our python module. All in the scope of one month. It looks like we succeeded in creating a generalised module. Well done!

Using our datapackage module we then proceeded to build a first version of an economical transformation toolkit, which we dubbed *[economics](http://github.com/tryggvib/economics/)* (yes, we are very creative when it comes to naming our python modules). At the moment it can do basic inflation computations using the CPI data and we made that available in the [Python Package Index](https://pypi.python.org/pypi/economics/) as well.

Now we're set to start implementing inflation adjustments in the OpenSpending platform. A huge thanks to all the economists, developers, data wrangler, and advisors for their help. July will be an exciting month!

### Blog migration

Another big change coming in July is a more standard blogging platform for OpenSpending. We have been using *[Jekyll](http://jekyllrb.com/)* to generate our blogs statically and serving them via the platform. We decided to move our blog back to [WordPress](http://wordpress.com/). This will make blog contributions even simpler since many people are more comfortable with WordPress than markdown.

We're not quite there yet (look for this change in July) but we called upon our task force to help us migrate the content and get the blog up to speed. We launched a IRC hack day where we collaborated on a [python script to migrate Jekyll content to WordPress](https://github.com/tryggvib/jekyll-to-wordpress/). The content has been migrated but there are some UI/UX tweaks we want to do before we launch our blog on WordPress.

If you know your way around WordPress and want to help. Let us know and we'll fill you in on what needs to be done.

### FarmSubsidy

In case you hadn't noticed we also launched and relaunched again the [FarmSubsidy project](http://farmsubsidy.openspending.org/) as part of OpenSpending. We initially launched an improved version of the project, after it was adopted by OpenSpending, on our servers but quickly noticed that we needed a dedicated server for the project.

So we took Farmsubsidy down for a couple of days while we sorted out the server issues and moved to a dedicated server. After reloading the data onto the new server we were able to relaunch Farmsubsidy so that the user experience should be better than it was in the first few days and now you can really start investigating how the EU subsidises farms.

### Thanks

As always there were loads of other changes and happenings in and around the OpenSpending project. We would love to get some help achieve even more in the coming months but we want to give a shout-out to all those who helped us in June.

Thanks to **Michael Bauer**, **Gunnlaugur Thor Briem**, **Lucy Chambers**, **Velichka Dimitrova**, **Martin Keegan**, **Dan Lemon**, **Andy Lulham**, **Tom Morris**, **Prakash Neupane**, **OpenRotterdam**, **Florian Oswald**, **Daniel O'Huiginn**, **Anders Pedersen**, **Rufus Pollock**, **Niels Erik Kaaber Rasmussen**, **Joel Rebello**, **Todd D. Robbins**, **Nils Toedtmann**, **Stefan Wehrmeyer**, and **Guo Xu** for their contributions this month (there are probably a lot more who've contributed somehow to this month's features so sorry in advance).
