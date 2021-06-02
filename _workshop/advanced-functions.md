---
title: Advanced Functions     # The title of the page
date: 0000-01-07    # Page order is set by date
---

5.1 Enhancing Data - LOOKING UP DATA FROM A URL
OpenRefine can retrieve data from URLs. This can be used in various ways, including looking up additional information from a remote service.

Typically this is a two step process,
retrieve data from a remote service
extract the relevant information from the data you have retrieved.

Use the drop down menu at any column heading and select ‘Edit column->Add column by fetching URLs’.
This will prompt you for a GREL expression to create a URL. The url uses values in your data to request a different data for each line. So you generally have the root of a url plus the value in a particular column.
The data retrieved will be stored in a cell in the new column.  You can then use OpenRefine transformations to extract relevant information from the data that has been retrieved.
Two specific OpenRefine functions used for this are: parseHtml() and parseJson()

Retrieving journal details from CrossRef via ISSN
Because retrieving data from external URLs takes time, this exercise targets a single line in the data. In reality you would want to run this over many rows (and probably go and do something else while it ran)
Select a single row from the data set which contains an ISSN by:
Clicking the star icon for the relevant row in the first column
Facet by Star
Choose the single row
In the ISSN column use the dropdown menu to choose ‘Edit column->Add column by fetching URLs’
Give the column a name e.g. “Journal details”

In this case we are going to use the CrossRef API.
https://github.com/CrossRef/rest-api-doc
API providers may impose rate limits or have other requirements for using their data, so it’s important to check the site’s documentation. CrossRef asks users to “specify a User-Agent header that properly identifies your script or tool and that provides a means of contacting you via email using ‘mailto:’.” User-agent headers provide administrators with user information that facilitates better administration and moderation of the API, and it is generally good etiquette to include a header with any API request.
To edit your User-Agent header:
Click ‘Show’ (next to ‘HTTP headers to be used when fetching URLs’). Note that OpenRefine has already populated the ‘User-Agent’ field
At the end of the existing text, add ; mailto:address@library.edu, using your own email address.
The syntax for requesting journal information from CrossRef is http://api.crossref.org/journals/{ISSN} where {ISSN} is replaced with the ISSN of the journal
In the expression box type the GREL "https://api.crossref.org/journals/"+value”
Click ‘OK’
You should see a message at the top on the OpenRefine screen indicating it is fetching some data, and how far it has got. Wait for this to complete. Fetching data for a single row should take only ten seconds or so, but fetching data for all rows will take longer. You can speed this up by modifying the “Throttle Delay” setting in the ‘Add column by fetching URLs’ dialog which controls the delay between each URL request made by OpenRefine. This is defaulted to a rather large 5000 milliseconds (5 seconds).
At this point you should have a new cell containing a long text string in a format called ‘JSON’ (this stands for JavaScript Object Notation, although very rarely spelt out in full).
OpenRefine has a function for extracting data from JSON (sometimes referred to as ‘parsing’ the JSON). The ‘parseJson’ function is explained in more detail at https://github.com/OpenRefine/OpenRefine/wiki/GREL-Other-Functions
In the new column you’ve just added use the dropdown menu to access ‘Edit column->Add column based on this column’
Add a name for the new column e.g. “Journal Title”
In the Expression box type the GREL value.parseJson().message.title
You should see in the Preview the Journal title displays

Using ‘Add column based on this column’ is simply that this allows you to retain the full JSON and extract further data from it if you need to. If you only wanted the title and did not need any other information from the JSON you could use ‘Edit cells->Transform…’ with the same GREL expression.

Looking up data by url is really useful. For larger datasets it can be slow. There are other ways to connect to external resources or services.
