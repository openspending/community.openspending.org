---
title: Annex - The Open Data Audit of EU Funds
---

As we have seen, detailed information on EU spending and beneficiaries managed directly by the Commission can be found on the EU FTS, but it only concerns 20% of the EU Budget. For the remaining 80%, there is no central place to go and one has to look at every external entity spending EU money.

In order to help in that task, we have set up the **Open Data audit of EU funds**. The aim of this census is to identify all existing datasets containing information on EU funds beneficiaries, and to assess whether or not data are available as open data.

The Open Data audit of EU funds is an ongoing and collaborative effort. First results can be found [here](https://docs.google.com/spreadsheets/d/1tkKxRlkW60-ylxdvxGkMlMq8BS4SRPR4QoEd72qgFwQ/edit#gid=2028897927).

* * * * *

{% for dataset in site.eu_datasets %}
[{{dataset.title}} ({{ dataset.coverage }})]({{ dataset.url }})
{% endfor %}

- [Return to Beginning](../)
- [Prev: Recommendations and Next Steps](../recommendations/)
- [Next: Annex - Legal Basis for the Establishment of the EU budget](../legal-basis/)

{% include_relative footnotes.md %}
