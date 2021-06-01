---
title: Transformations     # The title of the page
date: 0000-01-07    # Page order is set by date
---

Through facets, filters and clusters OpenRefine offers relatively straightforward ways of getting an overview of your data, and making changes where you want to standardise terms used to a common set of values.

However, sometimes there will be changes you want to make to the data that cannot be achieved in this way. Such types of changes include:

* Splitting data that is in a single column into multiple columns (e.g. splitting an address into multiple parts)
* Standardising the format of data in a column without changing the values (e.g. removing punctuation or standardising a date format)
* Extracting a particular type of data from a longer text string (e.g. finding ISBNs in a bibliographic citation)

To support this type of activity OpenRefine supports _Transformations_  which are ways of manipulating data in columns. Transformations are normally written in a special language called __GREL__ (General Refine Expression Language). GREL expressions are similar to Excel Formula, although they tend to focus on text manipulations rather than numeric functions.

Full documentation for the GREL is available at <https://docs.openrefine.org/manual/grelfunctions>. This tutorial covers only a small subset of the commands available.

### Common transformations
Some transformations are used regularly and are accessible directly through menu options, without having to type them directly.

Examples of some of these common transformations are given in the table below, with their ‘GREL’ equivalents.

Common Transformation | Action                                  | GREL expression |
--------------------- | --------------------------------------- | --------------- |
To Uppercase	        | Converts the current value to uppercase	| value.toUppercase() |
To Lowercase	        | Converts the current value to lowercase |	value.toLowercase() |
To Titlecase	        | Converts the current value to titlecase |	value.toTitlecase() |
Trim leading and trailing whitespace | Removes any ‘whitespace’ characters (e.g. spaces, tabs) from the start or end of the current value | value.trim() |

Sometimes there will be changes that are more structural.
* Splitting data from a single col into multiple cols (eg.an address)
* Standardising format of data in a col (e.g. date)

#### Remove whitespace in Publisher Column

* `Publisher > Text facet`
* See the multiple entries for one publisher
* `Edit cells > common transform > remove consecutive whitespace`

### Using GREL
To start writing GREL transformations:
* Select the column on which you wish to perform a transformation
* Choose `Edit cells > Transform…` to see the GREL screen.

You write transformations in the ‘Expression’ box and then can Preview the effect the transformation would have on the first 10 rows of your data. The transformation you type into the ‘Expression’ box has to be a valid GREL expression. The simplest expression is simply the word `value` by itself - which simply means ‘the value that is
currently in the column’ - that is, “make no change”.

GREL functions are written by giving a _value_ of some kind (a text string, a date, a number etc.) to a
GREL _function_. Some GREL functions take additional parameters or options which control how the
function works. GREL supports two syntaxes:
* `value.function(options)`
* `function(value, options)`

Either is valid, and which is used is completely down to personal preference.
Next to the `Preview` option are options to view:
* `History` - a list of transformations you’ve previously used with the option to reuse them
immediately or to ‘star’ them for easy access
* `Starred` - a list of transformations you’ve ‘starred’ via the ‘History’ view
* `Help` - a list of all the GREL functions and brief information on how to use them

#### Use GREL to standarise Publisher formatting
* Facet by `publisher`
* Select `Akshantala Enterprises` and `Society of Pharmaceutical Technocrats`
* Select multiple values in the facet with the `include` option
* See that the Titles for these are all in uppercase
* Click the dropdown menu on the `Title` column
* Choose `Edit cells->Transform...``
* In the Expression box type `value.toTitlecase()`

#### Undo / Redo and Apply / Extract
OpenRefine lets you undo, and redo, any steps you have taken in cleaning the data. This means you can always try out transformations and ‘undo’ if you need to. The way OpenRefine records the steps you have taken even allows you to take the steps you’ve carried out on one data set, and apply it to another data set by a simple copy and paste operation.

* `Undo` and `Redo` options are accessed via the lefthand panel
When you Undo, remaining steps will still show but are greyed out. However if you then start doing new transformations the greyed out steps will disappear and you’ll no longer have the option to redo those steps.

* To be reapply a set of steps or transformations you click on the `Extract` button. These are saved in JSON format. Select which one you want to save and copy the transformations into a .txt or .json file. You can then apply this from the same menu in a new dataset or project.

* The steps in the Undo / Redo menu of a project is saved with your project - it is not just during that session. So later on if you realise a transformation from an old project would be useful you can go back in and pull it out.
