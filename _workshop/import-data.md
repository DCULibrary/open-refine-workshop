---
title: Uploading Your Data     # The title of the page
date: 0000-01-03    # Page order is set by date
---

### Importing data
#### What kinds of data files can I import?
OpenRefine accepts data in a variety of formats including:
* TSV (tab-separated values)
* CSV (comma-separated values)
* Excel
* JSON (javascript object notation)
* XML
* Google Spreadsheet
(and more!)

#### How can I move my data into OpenRefine?
There are a number of ways to get data into Refine:
* select a file in a local directory or that you have downloaded
* by url if a dataset is hosted on the web (this is the method we wil use)
* copy/paste directly (in some text format like csv or json)

We will do it by uploading a file from a url <http://tiny.cc/dcuopenrefine>. This is taken from the __[*Carpentries*](https://carpentries.org)__ OpenRefine lessons, which this lesson is based on (see credits).

#### Create your first OpenRefine project (using provided data)
Once OpenRefine is launched in your browser
* Click `Create Project` from the left hand menu
* Select `Get data from This Computer`
* Click `Choose Files` or `Browse`(depending on your setup) and locate the `doaj-article-sample.csv` file which you have downloaded
* Click `Next >>`

The next screen (see below) gives you options to ensure the data is imported into OpenRefine correctly. The options vary depending on the type of data you are importing.

* Click in the `Character encoding` box and set it to `UTF-8`. This ensures that OpenRefine correctly interprets the imported data as UTF-8 encoded. If you don’t select this you may find that some special characters (e.g. smart quotation marks) are not displayed correctly.
* Ensure the first row is used to create the column headings by checking the box `Parse next 1 line(s) as column headers`
* OpenRefine will automatically select `Use character` to enclose cells containing column separators as this will place data in one cell where the values are enclosed in quotes from the source dataset
* From OpenRefine 3.4 onwards there is an option to `Trim leading & trailing whitespace from strings when importing separator-based files`. Keeping this checked will ensure that values like `English` and `English `, which differ by a single trailing space, are not treated as different values after the import
* Make sure the `Parse cell text into numbers, dates, ...` box is not checked, so OpenRefine doesn’t try to automatically detect numbers as it may cause errors such as confusion between date formats (e.g. DD/MM/YYYY vs MM/DD/YYYY)
* The `Project Name` box in the upper right corner will default to the title of your imported file. Click here and give your project a different name

Once you are happy click the `Create Project >>` button at the top right of the screen. This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.
