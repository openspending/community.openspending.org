---
layout: help
title: Development process
---

## Hacking on OpenSpending

### TL;DR

We welcome all hackers who want to contribute code, documentation, translations, issues/bug reports, comments or just about anything to [OpenSpending](http://openspending.org/). With your help OpenSpending can reach its goal of *tracking every government financial transaction across the world*.

When hacking on OpenSpending there are a few important cyberspace places you need to know about:

* [the developer mailing list](http://lists.okfn.org/mailman/listinfo/openspending-dev) (where you can find all OpenSpending developers)
* [the IRC channel](http://webchat.freenode.net/?channels=openspending) (for more informal chat and the monthly developer meeting)
* [the repositories](http://github.com/openspending/) (where code and documentation live)
* [the transifex project](https://www.transifex.com/projects/p/openspending/) (for translations)

## Development Community

### Mailing list

OpenSpending has a special developer mailing list: [openspending-dev@lists.okfn.org](http://lists.okfn.org/mailman/listinfo/openspending-dev).

This is where most of the discussions take place and where you can reach all openspending developers at once. If you have anything you'd like to ask, suggest or just talk about we suggest you subscribe to the developer mailing list and fire away.

### IRC channel

For realtime discussion we recommend you join our IRC channel **#openspending on Freenode**.

On our IRC channel you can reach many hardcore developers (or the most active developers at the moment). Not everyone will be there (that's what the developer mailing list is for) but if you have anything informal (that doesn't have to be archived) or just want to get in touch please join #openspending.

**The first Thursday of every month** our developer meeting takes place on our IRC channel. At that meeting we discuss the direction we as users and developers of OpenSpending want the project to head into (that is, on these meetings we discuss the bigger picture). You can voice your opinion on those meetings. There is no hierarchy and there are no dumb opinions.

### Code repositories

Development of OpenSpending mostly takes place on [GitHub](http://github.com/openspending/) in a few different repositories.

The four most important repositories for the OpenSpending platform are:

* [openspending/openspending](http://github.com/openspending/openspending): Contains the core openspending platform
* [openspending/openspendingjs](http://github.com/openspending/openspendingjs): Contains most of the javascript apps (e.g. visualisations) and code (e.g. model editor) related to openspending
* [openspending/osvalidate](http://github.com/openspending/osvalidate): Contains validation code and is essential to run the OpenSpending platform without problems
* [openspending/dotorg](http://github.com/openspending/dotorg): Contains all blog posts as well as documentation for the OpenSpending project

Of these four repositories [openspending/openspending](http://github.com/openspending/openspending), [openspending/openspendingjs](http://github.com/openspending/openspendingjs), and [openspending/dotorg](http://github.com/openspending/dotorg) are most active and where we need help the most.

There are a lot of other repositories and you might want to make changes to, like for example the [personal tax calculation](https://github.com/openspending/taxman), so you should also take a look at our complete list of [repositories on GitHub](http://github.com/openspending/).

### Translations

Localisation of OpenSpending happens on [Transifex](https://www.transifex.com/projects/p/openspending/).

Translations are really important. They help OpenSpending reach all corners of the world. Everyone should be able to access information that relates to them in their own mothertongue.

 We try to incorporate all translations that are nearly complete (that is we load translations that are 100% complete as a rule and we very often make exceptions to that rule if the translations are good enough).

There are of course some places in the code where we need help with internationalisation (preparing for localisation). Sometimes we've focused more on getting a feature to production than making it ready for localisation (so you can help us fix that).

## How do we develop?

### 1. Everything must be an issue

First rule is that every feature, bug fix or contribution must be based on an issue/feature request in our [issue tracker on GitHub](http://github.com/openspending/openspending/issues/). If you want to contribute something that hasn't been listed as an issue, just create one and start developing. It's better to discuss the idea/reasoning behind the issue/feature request in the issue tracker rather than mixing it in with code review/implementation discussions. It keeps our discussions cleaner and more focused.

### 2. Feature branches

Development should optimally take place in feature branches. That is when you want to work on a specific issue you should branch out of the master branch into a special branch that deals only with the feature you want to add or the bug you want to fix.

OpenSpending doesn't do *git rebase* (we've got some git history buffs amongst us). So you don't have to worry about rebasing. Just pull the master repository, branch it, and start hacking on the feature/bug fix.

### 3. Changes via pull request

Do you have code you want to contribute? Awesome! All changes to the code base must go through a pull request against the master branch. No code should ever be commited directly to the master branch. We therefore recommend you create a feature branch based on the issue in the issue tracker you want to work on. OpenSpending's core developers will take it from there.

### 4. Code review

The pull requests sent in, must be reviewed by a core developer and in the case when a core developer creates a pull request by another core developer than the one who committed the changes (so a core developer cannot review her/his own code). The reviewer should try and foresee any problems with the implementation, remind the developer about translations, discuss code quality or raise any other issues. This should all be done with constructive criticism.

Don't be afraid of code reviews or any criticism you might get. Use them to become a better developer! If you feel the reviewer isn't being constructive let her/him know so she/he can improve her/his future reviews (we're all trying to be constructive but that might take some practice or words might come out wrong online). The code reviewer is not always correct so if you feel the reviewer is wrong, protect and argue for your implementation (and the reviewer can use it to become a better reviewer/developer).

### 5. Travis CI

We use [Travis](http://travis-ci.org/) for continous integration (so we can deploy features as soon as they're ready instead of working with versions). All pull requests and merges with master are automatically tested with the help of Travis. That means we need to have good tests (and we're always trying to improve our test cases). This helps us with code reviews and prevents us from pushing broken (non-tested) code to production.

### 6. Staging server

Before we push anything to production we run it on our staging server for some time. This is just to be sure everything is as it should be (in case tests don't catch something). Core developers take a look at the staging version before it can be pushed to production. This means we have code reviews, tests and a staging server to prevent anything from happening to production. We have a lot of different sites that rely on [http://openspending.org](http://openspending.org) (the primary instance of the platform) so we need to be absolutely sure we won't break anything.

### 7. Production

When we're absolutely sure we're really unlikely to break anything, one of the core developers pushes it to production on [http://openspending.org](http://openspending.org).

### Notes

As you can see the process is quite elaborate and it might take some time for changes to go live but every step of the process is open so you should be able to follow your changes from the original commit to the production server.

If at any point you feel things are going slowly you should let core developers know via the developer mailing list or on the IRC channel.

Translations can happen anywhere in the process and we try to deploy them as soon as they're ready (after being included once deployment becomes automatic).

## Where can you start?

We've labeled issues in our [main GitHub repository](http://github.com/openspending/openspending) that are suitable for volunteers. There are a three different stages: **volunteer-simple** (for beginners), **volunteer-advanced** (if you're looking for a challenge) and **volunteer-hard** (heroes apply here). We've tried to label them so that you can find an issue based on your knowledge of the OpenSpending code base and your coding skills.

Here's a list of the current issues where you can help OpenSpending:

<table id="github-issues" class="table">
  <tr><th>Label</th><th>Issue</th></tr>
</table>

<script src="http://openspending.org/static/openspendingjs/lib/vendor/jquery.js"></script>
<script type="text/javascript">
  var issues = $("#github-issues");
  var github = "https://api.github.com/repos/openspending/openspending/issues"
  var labels = [{name:"volunteer-simple", colour:"#d7e102"},
                {name:"volunteer-advanced", colour:"#e102d8"},
                {name:"volunteer-hard", colour:"#02e10c"}];
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
                        + '; text-shadow: 0 -1px 0 rgba(0, 0, 0, 0.25);">'
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
</script>
