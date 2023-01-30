---
title: Facets and Clusters     # The title of the page
nav: Facets & Clusters
date: 0000-01-04    # Page order is set by date
---

### Facets
Facets are one of the most useful features in OpenRefine. They can help you
* get an overview of your data in a project
* see if there are issues or inconsistencies
* start to take action to fix those inconsistencies

A facet groups all the values that appear in a column, and then allows you to filter the data by these values (or look at each group records at a time) and apply batch edits. There are different types but the first one we’ll look at is called a __*text facet*__

#### Perform a text facet
* Click `Publisher > Facet > Text Facet`
* The facet appears in the left hand panel. We see all the publishers listed
* If we switch to `count` we can see what the most frequent one is
* We can also click on any one result to filter to just those results
* To include or exclude other results we can use the `Include / Exclude / Invert` options which appear when you put your mouse over a value in the Facet

There are other types of facets - numeric, scatterplot, timeline - which require the data to be in formats other than text. We'll look at formats in OpenRefine shortly.

#### Facet by duplicate
* Facet by duplicate on title (spots possible duplicate entry)

#### Facet by blank
* Facet by blank on publisher

#### Use facets to batch edit data
As well as giving you this clear view on data you can also use facets to start to work on the data.
* Do a `text facet` on `Language`
* Fix `EN` and `English` variation

### Working with filtered data
It is very important to note that when you have filtered the data displayed in OpenRefine (like we did above by selecting facet results) any operations you carry out will apply only to the rows that match the filter i.e. the data currently being displayed.
An example of this is in use is if you wish to remove rows that match a filter, you can do this as follows:
* Filter the data using Facets or Filters
* Clicking on the drop down menu under the `All` column heading
* Choose `Edit rows > Remove all matching rows`
* This will remove all rows that were selected or displayed by the filter

----------------------------
### Clustering
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
