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

#### Use GREL to standarise Publisher formatting
* Facet by `publisher`
* Select `Akshantala Enterprises` and `Society of Pharmaceutical Technocrats`
* Select multiple values in the facet with the `include` option
* See that the Titles for these are all in uppercase
* Click the dropdown menu on the `Title` column
* Choose `Edit cells->Transform...``
* In the Expression box type `value.toTitlecase()`
