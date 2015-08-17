---
section: get-involved
lead: true
title: Development process
authors:
- Neil Ashton
---
Discussions are the backbone of a successful development, especially in a collaborative project like OpenSpending. There are many ways to communicate, and we rely the most on the *open source standard* of mailing lists and an IRC channel.

However, we expand on those reliable mediums by using [GitHub](http://github.com) to host our source code repositories and as our issue tracker. GitHub helps us to keep the discussions about specific issues and commits more focused.

We also believe that being able to converse about the software in your own language is really important. That's why we see localisation (translations) as a fundamental communication channel for the project.

Our four core communication channels are therefore: **mailing lists**, **IRC channel**, **the repositories and issue tracker**, and **the translation platform**.

#### Mailing lists

OpenSpending has a discussion list where users and developers can meet in cyberspace and discuss issues and ideas related to OpenSpending: [openspending@lists.okfn.org](http://lists.okfn.org/mailman/listinfo/openspending).

On the discussion list we try to keep discussions relatively free of technical implementations. It's supposed to be a place where users and developers have a common ground for their discussions. The discussion list is key to understanding user requirements (and transform them into feature requests/bugs). For that you need a good eye to notice requirements in free flow discussions. If you think you can, please join the discussion list and read about our issue tracker below.

For technical implementations or other development related discussions OpenSpending has a special developer mailing list: [openspending-dev@lists.okfn.org](http://lists.okfn.org/mailman/listinfo/openspending-dev).

This is where most of the development specific discussions take place and where you can reach all openspending developers at once. If you want to help and you have anything you'd like to ask, suggest or just talk about we suggest you subscribe to the developer mailing list and fire away.

#### IRC channel

For realtime discussion we recommend you join our IRC channel **#openspending on Freenode**.

On our IRC channel you can reach many hardcore developers (or the most active developers at the moment). Not everyone will be there (that's what the developer mailing list is for) but that shouldn't keep you from popping in on #openspending to say hello.

**The first Thursday of every month** our developer meeting takes place on our IRC channel. At that meeting we discuss the direction we as users and developers of OpenSpending want the project to head into (that is, on these meetings we discuss the bigger picture). You can voice your opinion on those meetings. There is no hierarchy and there are no dumb opinions.

### Repositories and issue tracker

Development of OpenSpending mostly takes place on [GitHub](http://github.com/openspending/) in a few different repositories.

The three most important repositories for the OpenSpending platform are:

* [openspending/openspending](http://github.com/openspending/openspending): Contains the core openspending platform
* [openspending/openspendingjs](http://github.com/openspending/openspendingjs): Contains most of the javascript apps (e.g. visualisations) and code (e.g. model editor) related to openspending
* [openspending/osvalidate](http://github.com/openspending/osvalidate): Contains validation code and is essential to run the OpenSpending platform without problems

Of these three repositories [openspending/openspending](http://github.com/openspending/openspending) and [openspending/openspendingjs](http://github.com/openspending/openspendingjs) are most active and where we need help the most.

There are a lot of other repositories and you might want to make changes to, like for example the [personal tax calculation](https://github.com/openspending/taxman), so you should also take a look at our complete list of [repositories on GitHub](http://github.com/openspending/).

This is also where our issue tracker is located. The most active issue tracker (and hence the best one to raise and discuss issues in) is the issue tracker for the [core openspending platform](http://github.com/openspending/openspending/issues).

#### Translations

Localisation of OpenSpending happens on [Transifex](https://www.transifex.com/projects/p/openspending/).

Translations are really important. They help OpenSpending reach all corners of the world. Everyone should be able to access information that relates to them in their own language.

This is also important to the development process. Even though most developers understand English, being able to use the software in our own language deepens our understanding of it and can give a new meaning to the development.

That's why translators are so important. They help both users *and* developers. We try to incorporate all translations that are nearly complete (we load translations that are 100% complete as a rule and we very often make exceptions to that rule if the translations are good enough).

There are of course some places in the code where we need help with internationalisation (preparing for localisation). Sometimes we've focused more on getting a feature to production than making it ready for localisation (but you can help us fix that).

#### How do we develop?

##### 1. Everything must be an issue

First rule is that every feature, bug fix or contribution must be based on an issue/feature request in our [issue tracker on GitHub](http://github.com/openspending/openspending/issues/). If you want to contribute something that hasn't been listed as an issue, just create one and start developing. It's better to discuss the idea/reasoning behind the issue/feature request in the issue tracker rather than mixing it in with code review/implementation discussions. It keeps our discussions cleaner and more focused.

##### 2. Feature branches

Development should optimally take place in feature branches. That is when you want to work on a specific issue you should branch out of the master branch into a special branch that deals only with the feature you want to add or the bug you want to fix.

OpenSpending doesn't do *git rebase* (we've got some git history buffs amongst us). So you don't have to worry about rebasing. Just pull the master repository, branch it, and start hacking on the feature/bug fix/documentation addition or whatever you want to contribute.

##### 3. Changes via pull request

Do you have code/documentation you want to contribute? Awesome! All changes to the code base/documentation must go through a pull request against the master branch. No code should ever be commited directly to the master branch. We therefore recommend you create a feature branch based on the issue in the issue tracker you want to work on. When you're done, create a pull request and OpenSpending's core developers will take it from there.

##### 4. Review

The pull requests sent in, must be reviewed by a core developer and in the case when a core developer creates a pull request by another core developer than the one who committed the changes (so a core developer cannot review her/his own contributions). The reviewer should try and foresee any problems with the implementation, remind the developer about translations, discuss quality or raise any other issues. This should all be done with constructive criticism. We have some general guidelines on [how to perform code reviews for OpenSpending](../review/).

Don't be afraid of reviews or any criticism you might get. Use them to become a better developer/contributor! If you feel the reviewer isn't being constructive let her/him know so she/he can improve her/his future reviews (we're all trying to be constructive but that might take some practice or words might come out wrong online). The reviewer is not always correct so if you feel the reviewer is wrong, protect and argue for your contribution (and the reviewer can use it to become a better reviewer/developer).

##### 5. Travis CI

We use [Travis](http://travis-ci.org/) for continous integration (so we can deploy features as soon as they're ready instead of working with versions). All pull requests and merges with master are automatically tested with the help of Travis. That means we need to have good tests (and we're always trying to improve our test cases). This helps us with reviews and prevents us from pushing broken (non-tested) code to production.

##### 6. Staging server

Before we push anything to production we run it on our staging server for some time. This is just to be sure everything is as it should be (in case tests don't catch something) and can be performed as part of code review as well. Core developers take a look at the staging version before it can be pushed to production. This means we have reviews, tests and a staging server to prevent anything from happening to production. We have a lot of different sites that rely on [http://openspending.org](http://openspending.org) (the primary instance of the platform) so we need to be absolutely sure we won't break anything.

##### 7. Production

When we're absolutely sure we're really unlikely to break anything, one of the core developers pushes it to production on [http://openspending.org](http://openspending.org).

##### Notes

As you can see, the process is quite elaborate and it might take some time for changes to go live but every step of the process is open so you should be able to follow your changes from the original commit to the production server.

If at any point you feel things are going slowly you should let core developers know via the developer mailing list or on the IRC channel.

Translations can happen anywhere in the process and we try to deploy them as soon as they're ready (after being included once deployment becomes automatic).

#### Where can you start?

We've labeled issues in our [main GitHub repository](http://github.com/openspending/openspending) that are suitable for volunteers. There are a three different stages: **volunteer-simple** (for beginners), **volunteer-advanced** (if you're looking for a challenge) and **volunteer-hard** (heroes apply here). We've tried to label them so that you can find an issue based on your knowledge of the OpenSpending code base and your coding skills.

Here's a list of the current issues where you can help OpenSpending with some coding:

<table class="table" id="github-issues">
<tbody>
<tr>
<th>Label</th>
<th>Issue</th>
</tr>
</tbody>
</table>
<script type="text/javascript" src="http://openspending.org/static/openspendingjs/lib/vendor/jquery.js"></script>
<script type="text/javascript">// <![CDATA[
var issues = $("#github-issues");
  var github = "https://api.github.com/repos/openspending/openspending/issues"
  var labels = [{name:"Volunteer: simple", colour:"#bfe5bf"},
                {name:"Volunteer: medium", colour:"#fad8c7"},
                {name:"Volunteer: hard", colour:"#f7c6c7"}];
  for (idx in labels) {
    var label = labels[idx];
    $.ajax({
      url: github,
      data: {labels:label.name},
      success: function(data) {
        $.each(data, function(i) {
          issues.append('<tr><td>'
                        + '<span class="label" style="background:'
                        + label.colour
                        + '; color: #222222; text-shadow: 0 -1px 0 rgba(255, 255, 255, 0.75);">'
                        + label.name
                        + '</td><td><a href="'
                        + this.html_url
                        + '">'
                        + this.title
                        + '</a></td></tr>'
                       );
        });
      },
      async: false,
    });
  }
// ]]></script>
