---
title: Advanced Functions     # The title of the page
date: 0000-01-07    # Page order is set by date
---

### Enhancing Data 1: Look up data from a URL
OpenRefine can retrieve data from URLs. This can be used in various ways, including looking up additional information from a remote service. Typically this is a two step process:
* retrieve data from a remote service
* extract the relevant information from the data you have retrieved

Use the drop down menu at any column heading and select `Edit column->Add column by fetching URLs`. This will prompt you for a GREL expression to create a url. The url uses values in your data to request a different data for each line. So you generally have the root of a url plus the value in a particular column. The data retrieved will be stored in a cell in the new column.  You can then use OpenRefine transformations to extract relevant information from the data that has been retrieved.
Two specific OpenRefine functions used for this are: `parseHtml()` and `parseJson()`

### Retrieving journal details from CrossRef via ISSN
Because retrieving data from external URLs takes time, this exercise targets a single line in the data. In reality you would want to run this over many rows (and probably go and do something else while it ran)
Firstly we will will filter to a single row from the data set which contains an ISSN by:
* Clicking the star icon for the relevant row in the first column
* Facet by Star
* Choose the single row
* In the `ISSN` column use the dropdown menu to choose `Edit column->Add column by fetching URLs`
* Give the column a name e.g. "Journal details"

In this case we are going to use the CrossRef API <https://github.com/CrossRef/rest-api-doc>
API providers may impose rate limits or have other requirements for using their data, so it’s important to check the site’s documentation. CrossRef asks users to “specify a User-Agent header that properly identifies your script or tool and that provides a means of contacting you via email using ‘mailto:’.” User-agent headers provide administrators with user information that facilitates better administration and moderation of the API, and it is generally good etiquette to include a header with any API request.

To edit your User-Agent header:
* Click `Show` (next to `HTTP headers to be used when fetching URLs`). Note that OpenRefine has already populated the `User-Agent` field
* At the end of the existing text, add ; mailto:address@library.edu, using your own email address.
* The syntax for requesting journal information from CrossRef is http://api.crossref.org/journals/{ISSN} where {ISSN} is replaced with the ISSN of the journal
* In the expression box type the GREL `"https://api.crossref.org/journals/"+value”`
* Click `OK`
You should see a message at the top on the OpenRefine screen indicating it is fetching some data, and how far it has got. Wait for this to complete. Fetching data for a single row should take only ten seconds or so, but fetching data for all rows will take longer. You can speed this up by modifying the `Throttle Delay` setting in the `Add column by fetching URLs` dialog which controls the delay between each URL request made by OpenRefine. This is defaulted to a rather large 5000 milliseconds (5 seconds).

At this point you should have a new cell containing a long text string in a format called JSON (this stands for JavaScript Object Notation).
OpenRefine has a function for extracting data from JSON (sometimes referred to as _parsing_ the JSON). The `parseJson` function is explained in more detail at <https://github.com/OpenRefine/OpenRefine/wiki/GREL-Other-Functions>
* In the new column you’ve just added use the dropdown menu to access `Edit column->Add column based on this column`
* Add a name for the new column e.g. "Journal Title"
* In the Expression box type the GREL `value.parseJson().message.title`
* You should see in the Preview the Journal title displays

Using `Add column based on this column` is simply that this allows you to retain the full JSON and extract further data from it if you need to. If you only wanted the title and did not need any other information from the JSON you could use `Edit cells->Transform…` with the same GREL expression.

Looking up data by url is really useful. For larger datasets it can be slow. There are other ways to connect to external resources or services.

-----------------------

### Enhancing Data 2: Reconciliation

A _reconciliation_ service is a web service that, given some text which is a name or label for something, returns a ranked list of potential entities matching the criteria. The candidate text does not have to match each entity's official name perfectly, and that's the whole point of reconciliation--to get from ambiguous text name to precisely identified entities.

This is quicker and more advanced than the ‘by url’ method. But it requires the resource you are linking to to provide its data as a reconciliation service. You can find some examples here: <https://github.com/OpenRefine/OpenRefine/wiki/Reconcilable-Data-Sources>
These services can directly be added to OpenRefine using their URL by clicking Reconcile -> Add Standard Service.
https://reconciliation-api.github.io/testbench/

In this exercise you are going to use the __VIAF__ Reconciliation service written by Jeff Chiu. Jeff offers two ways of using the reconciliation service - either via a public service he runs at <http://refine.codefork.com>, or by installing and running the service locally using the instructions at <https://github.com/codeforkjeff/conciliator>.

Once you have chosen which service you are going to use:

* In the `Publisher` column use the dropdown menu to choose `Reconcile->Start Reconciling`
* If this is the first time you’ve used this particular reconciliation service, you’ll need to add the details of the service now
* Click `Add Standard Service…` and in the dialogue that appears enter:
“http://refine.codefork.com/reconcile/viaf” for Jeff’s public service
* You should now see a heading in the list on the left hand side of the Reconciliation dialogue called “VIAF Reconciliation Service”
* Click on this to choose to use this reconciliation service
* In the middle box in the reconciliation dialogue you may get asked what type of ‘entity' you want to reconcile to - that is, what type of thing are you looking for. In this case choose `Corporate Name` (it seems like the VIAF Reconciliation Service is slightly intelligent about this and will only offer options that are relevant)
* At the bottom uncheck  `Auto-match candidates with high confidence`. This can be a time saver, but in this case you are going to uncheck it so you can see the results before a match is made
* Now click `Start Reconciling`

Reconciliation is an operation that can take a little time if you have many values to look up. However, in this case there are only 6 publishers to check, so it should work quite quickly.

Once the reconciliation has completed two Facets should be created automatically:
* `Publisher: Judgement`
* `Publisher: best candidate’s score`

These are two of several specific reconciliation facets and actions that you can get from the `Reconcile` menu (from the column drop down menu).
* Close the `Publisher: best candidate’s score` facet

If you look at the Publisher column, you should see some cells have found one or more matches - the potential matches are shown in a list in each cell. Next to each potential match there is a ‘tick’ and a ‘double tick’. To accept a reconciliation match you can use the ‘tick’ options in cells. The ‘tick’ accepts the match for the single cell, the ‘double tick’ accepts the match for all identical cells.

* Create a `text facet` on the `Publisher` column
* Choose `International Union of Crystallography`
* In the `Publisher` column you should be able to see the various potential matches. Clicking on a match will take you to the VIAF page for that entity.
* Click a ‘double tick’ in one of the `Publisher column` cells for the option `International Union of Crystallography`. This will accept this as a match for all cells - you should see the other options all disappear
* Check the `Publisher: Judgement` facet. This should now show that 858 items are ‘matched’ (if this does not update, try refreshing the facets)

We could do these one by one, but if we are confident with the matches, there is an option to accept all:
* Remove all filters/facets from the project so all rows display
* In the `Publisher` column use the dropdown menu to choose `Reconcile->Actions->Match each cell to its best candidate`

As well as these services, some data providers have gone further and written openrefine _extensions_. Whether you use these or which ones you use will depend a lot on your dataset and subject area and what you are trying to achieve. But for now it is really to know that you can do this with OpenRefine.
A list of Extensions (not necessarily complete) is given on the OpenRefine downloads page at http://openrefine.org/download.html

-----------------------------
