---
title: Getting Started     # The title of the page
nav: Getting Started
date: 0000-01-03    # Page order is set by date
---

## Importing data

#### What kinds of data files can I import?

OpenRefine accepts data in a variety of formats including:
* TSV (tab-separated values)
* CSV (comma-separated values)
* Spreadsheet (e.g. excel or google sheets)
* JSON (javascript object notation)
* XML

#### How can I move my data into OpenRefine?

![Import screen](assets/images/Import.png)
There are a number of ways to get data into Refine:
* select a file in a local directory or that you have downloaded
* by url if a dataset is hosted on the web (this is the method we wil use)
* copy/paste directly (in some text format like csv or json)

We will do it by uploading a file from a url <https://github.com/LibraryCarpentry/lc-open-refine/raw/gh-pages/data/doaj-article-sample.csv>. This is taken from the __[*Carpentries*](https://carpentries.org)__ OpenRefine lessons, which this lesson is based on (see [credits](credits.md).

## Create your first OpenRefine project

Once OpenRefine is launched in your browser:
* Click `Create Project` from the left hand menu
* Select `Web Addresses (URLs)`
* Enter `https://github.com/LibraryCarpentry/lc-open-refine/raw/gh-pages/data/doaj-article-sample.csv` in the text box
* Click `Next >>`

OpenRefine should give you a preview of how it will parse your dataset and gives various options to ensure the data is imported into OpenRefine correctly. 

![parsing screenshot](assets/images/parsing.png)

The exact options to choose vary depending on the type of data you are importing. For this exercise we'll make a few checks:

* Click in the `Character encoding` box and set it to `UTF-8`. This can be important if you have a dataset that uses certain special characters.
* Ensure the first row is used to create the column headings by checking the box `Parse next 1 line(s) as column headers` (this should already be checked)
* Make sure the `Parse cell text into numbers, dates, ...` box is not checked. We will work through this during the exercises.
* The `Project Name` box in the upper right corner will default to the title of your imported file. Click here and give your project a different name

Once you are happy click the `Create Project >>` button at the top right of the screen. This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.

#### Going Further
* Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.
* Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a `record path` i.e. the parts of the file that will form the data rows in the OpenRefine project.

----------------------------

### Layout of OpenRefine
OpenRefine displays data in a _tabular_ format. Each row will usually represent a _record_ in the data, while each column represents a type or field of information. This is similar to how you might view data in a spreadsheet or a database. As with a spreadsheet, the individual bits of data live in _cells_ at the intersection of a row and a column.

### Working with data
* OpenRefine displays a limited number of rows at one time. You can adjust this (from 5 rows up to 1000) at the top left of the table.

* In OpenRefine we will not generally work with our data record by record; instead we’ll find ways to group or filter it into batches and then work within those batches.

* We will mostly use the drop down menus at the top of each column to carry out operations. Click on the small downward arrow to bring up a menu of options for that column. When you select an option in a column (e.g. to make a change to the data), it will affect all the cells in that column. If you want to make changes across several columns, you do this one column at a time.

### Moving Columns
If you didn’t have the correct column as the first column you could fix this in OpenRefine by
* `Title > Edit column > Move column to beginning`
If you are reordering columns like this at the start an easier way to do it is use the `All` menu on the left hand side of the table:
* `All > Edit Columns > Reorder / Remove Columns`
This is also a handy way to remove multiple columns if your raw dataset has lots of data not relevant for you.

### Rows and Records
OpenRefine has two modes of viewing data: _Rows_ and _Records_. It defaults to _Rows_ mode.
* A row is a single line of your project.
* A record is a combination of one or multiple rows indentifying a unique object and sharing the same first column
At the moment the rows and records numbers are the same. To show how this can be different we'll look for cells which have multiple values and split it across multiple rows.
* The `author` column is showing lots of cells with more than one author.
* Click on `edit` for closer look at what is in that column. Notice the separator is a | or 'pipe' character.
* `Author > Edit cells > split multi valued cells`
* Toggle the row/record view to now see the count difference
* `Author > Edit cells > join multi valued cells`
* And our row and record counts are once again the same.

In these multivalued cells the character separating each value is called a _separator_ or _delimiter_. Choose a good separator - a comma separator in the author field would cause problems!! Generally you look to __choose a separator that is not in your data values__.

__Exercise__
* Try doing the same thing in the `subject` field - `split` and `join`

So that is some initial reorganising. Next we’ll look at refining functions - faceting filtering, and clustering

## 💡 Key Points

✅ Use the Create Project option to import data

✅ You can control how data imports using options on the import screen

✅ Several files types may be imported into OpenRefine.

✅ OpenRefine uses rows and columns to display data. Records mode links multiple rows to a single record.

✅ Most work in OpenRefine is performed via a drop down at the top of each column

✅ Split and join multi-valued cells to modify the individual values within them.

✅ When creating multi-valued cells in your data, choose your separator carefully
