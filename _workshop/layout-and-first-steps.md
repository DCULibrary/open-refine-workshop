---
title: Layout / First Steps     # The title of the page
date: 0000-01-04    # Page order is set by date
---

### Layout of OpenRefine
OpenRefine displays data in a _tabular_ format. Each row will usually represent a _record_ in the data, while each column represents a type or field of information. This is similar to how you might view data in a spreadsheet or a database. As with a spreadsheet, the individual bits of data live in _cells_ at the intersection of a row and a column.

### Working with data
* OpenRefine displays a limited number of rows at one time. You can adjust this (from 5 rows up to 50) at the top left of the table.

* That’s because in OpenRefine we will not generally work with our data record by record; instead we’ll find ways to group or filter it into batches and then work within those batches.

* We will mostly use the drop down menus at the top of each column to carry out operations. Click on the small downward arrow to bring up a menu of options for that column. When you select an option in a column (e.g. to make a change to the data), it will affect all the cells in that column. If you want to make changes across several columns, you do this one column at a time.

### Moving Columns
If you didn’t have the correct column as the first column you could fix this in OpenRefine by
* `Title > Edit column > Move column to beginning`
If you are reordering columns like this at the start an easier way to do it is use the `All` menu on the left hand side of the table:
* `All > Edit Columns > Reorder / Remove Columns`
This is also a handy way to remove multiple columns if your raw dataset has lots of data not relevant for you.

### Rows and Records
OpenRefine has two modes of viewing data: _Rows_ and _Records_. It defaults to _Rows_ mode, where each row represents a single record in the data set - in this case, an article. In _Records_ mode, OpenRefine can link together multiple rows as belonging to the same Record.
* A row is a single line of your project.
* A record is a combination of one or multiple rows indentifying a unique object and sharing the same first column
At the moment the rows and records numbers are the same. To show how this can be different we'll look for cells which have multiple values and split it across multiple rows.
* The `author` column is showing lots of cells with more than one author.
* Click on `edit` for closer look at what is in that column. Notice the separator is a semi-colon.
* `Author > Edit cells > split multi valued cells`
* Toggle the row/record view to now see the count difference
* `Author > Edit cells > join multi valued cells`
* And our row and record counts are once again the same.

In these multivalued cells the character separating each value is called a _separator_ or _delimiter_. Choose a good separator - a comma separator in the author field would cause problems!! Generally you look to __choose a separator that is not in your data values__.

__Exercise__
* Try doing the same thing in the `subject` field - `split` and `join`

So that is some initial reorganising. Now we’ll look at refining functions - faceting filtering, and clustering
