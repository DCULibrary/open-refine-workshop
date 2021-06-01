---
title: Facets     # The title of the page
date: 0000-01-05    # Page order is set by date
---

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
