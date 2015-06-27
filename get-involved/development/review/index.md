---
section: get-involved
lead: true
title: Code reviews
authors:
- Neil Ashton
---
Many different sites rely on OpenSpending, and one of the most important things we do to avoid deploying faulty code to our production servers is code reviews. Every commit that is merged into *master* has to be reviewed by another person. *You* can be that reviewer and thus help improve the overall quality of OpenSpending.

#### What do I need to know to review code?

We mainly have two different projects with different skill requirements:

* [OpenSpending](http://github.com/openspending/openspending) - Requires knowledge of Python
* [OpenSpendingJS](http://github.com/openspending/openspendingjs) - Requires knowledge of Javascript

For both of those projects, knowledge about web development pitfalls is also good.

#### How do I do code reviews?

First of all, join our [developer mailing list](http://lists.okfn.org/mailman/listinfo/openspending-dev) and/or IRC channel #openspending on Freenode.

Code reviews are performed on *pull requests*. Each pull request can have many reviwers even though only one is enough for merging (more is better).

Keep all discussions related to the code review in the comments system on [github](http://github.com) for that particular pull request. This keeps them both public and in context. For bigger issues use the *dev mailing list*.

Here are a few things to keep in mind when doing code review:

* Use constructive criticism (i.e. don't be a jerk - that goes for the developer as well)
* Every pull request should solve/fix an issue in the [issue tracker](http://github.com/openspending/openspending/issues/)
* Do you see any bugs in the code?
* Is the code readable/maintainable? (we don't want obfuscated code)
* Is it well commented? (Too many comments is better than no comments)
* Do the changes have good test coverage?
* At least every feature should be tested (if possible just about everything)
* Removing or changing tests should be avoided at all costs (it demands some good explanation)
* Does this follow code conventions?
* We follow [OKF's Coding Standards](http://wiki.okfn.org/Coding_Standards)
* Has the developer thought about i18n or l10n (can all strings be translated)?

#### Can I try it out?

We have a [staging server](http://staging.openspending.org) (it's turned off by default) where you can try out the pull request (since reading the code can be hard). Just request that the pull request be put on the staging server and the core developers will take care of it.

#### OK, I've reviewed a pull request, now what?

We use the [Apache Voting Process](http://apache.org/foundation/voting.html) for code reviews. You might know it as *+1* voting. You express your review with a number between -1 and 1 where -1 is a veto and +1 is approval.

We differ from the Apache foundation in how many +1s the pull request must have before being merged. For Apache it's 3 (and no -1) for OpenSpending we only require a single +1 (and no -1). This is because of the different sizes of the communities. You can retract you -1 vote at any point.

When rejecting a pull request state the reason why so the developer can improve the code.

#### Any questions?

Just ask on the [developer mailing list](http://lists.okfn.org/mailman/listinfo/openspending-dev) or our IRC channel #openspending on Freenode.
