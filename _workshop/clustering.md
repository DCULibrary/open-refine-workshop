---
title: Clustering     # The title of the page
date: 0000-01-06    # Page order is set by date
---

Clustering is another way to clean your data - somewhat similar to the text facet but it uses algorithms to detect similar values and suggest merges rather than the more manual selection of facets. It looks for patterns of variation without you needing to do quite so much detective work. So for very large datasets this can be really useful.

* Split the `author` values again (using `Edit cells -> Split multi-valued cells`, using the pipe ( &#124; ) character as the separator)
* On the `author` column `Edit cells > cluster and edit`

The default method (`fingerprinting`) looks at variations in whitespace and case. It is pretty good at pulling out the most common and most obvious inconsistencies. After you’ve applied it and merged them you can try one of the other algorithms. More info on the heuristics that are used here
<https://github.com/OpenRefine/OpenRefine/wiki/Clustering-In-Depth>

It’s quite helpful that you can have a good look at them and pick individually where you want to make these batch changes.

The clustering is syntactic only - not semantic, so not looking at meaning. You might want to do this with subject terms. To do that you would have to use _reconciliation_ where OpenRefine can link with another dataset. We will look at that later.

After whatever clustering you have done you `join multiple values` in the `author` cell

OpenRefine is useful to _surface_ near-matches, but it does not automate the work of collapsing them into normalized values. Instead, it focuses one’s attention and labour on exactly that activity. In our initial version of computer-assisted data curation, you still have to touch each data point.

### Key Points
* Clustering is a way of finding variant forms of the same piece of data within a dataset (e.g. different spellings of a name)
* There are a number of different Clustering algorithms that work in different ways and will produce different results
* The best clustering algorithm to use will depend on the data
* Using clustering you can replace varying forms of the same data with a single consistent value
