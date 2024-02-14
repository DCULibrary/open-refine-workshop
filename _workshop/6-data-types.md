---
title: Data Types     # The title of the page
nav: Data Types
date: 0000-01-06    # Page order is set by date
---

There are five data types in OpenRefine:
* Text
* Number
* Date
* Boolean
* Array

### Working with Dates

OpenRefine tends to default to seeing content as text. But you can turn them into these other data types. This project has a date field which is actually being treated as a string. With a transform we can tell it that this is a date

* On the `Date` column use the dropdown menu to select `Edit cells -> Transform`
* In `Expression` box type `value.toDate()` and press `OK`

Note how the values are now displayed in green and follow a standard convention for their display format (ISO 8601) - this indicates they are now stored as `date` data types in OpenRefine. We can now carry out functions that are specific to Dates

* On the `Date` column dropdown select `Edit column->Add column based on this column`. Using this function you can create a new column, while preserving the old column
* In the New column name type `Formatted Date`
* In the ‘Expression’ box type the GREL expression `value.toString("dd MMMM yyyy")`

### Arrays

An _array_ is a list of values or strings that can be reordered or manipulated. They only come into play when performing transformations. Arrays cannot be stored in a cell in OpenRefine. In GREL it is the `split` function which creates an array (similar to the way we split cells earlier).
* Go to `subject` column
* `Edit cells > Transform...`
* `value.split("&#124;")`

Like earlier, the `&#124;` is whatever is the separator already there. The preview shows the column values square brackets `[` at the end (denoting this as an array) and quote marks around each individual value in the array. 

There are various [array functions](https://openrefine.org/docs/manual/grelfunctions#array-functions) that can be used to do different things. We can try a couple out here just to see the results in the preview screen (without clicking `Ok`)

#### length()
- `value.split("&#124;").length()` will return the number of values in each array

#### uniques()
- `value.split("&#124;").uniques` will remove any duplicate values in each array

Let's instead try `sort()`, another array function which organises the values in an array alphabetically:

* `value.split("|").sort().join("|")`

So that didn't quite work as planned, The `sort` function is case sensitive. So we’ll fix that first:
* `value.split(“|”).join(“ | “).toTitlecase()`
* `value.split(“ | ”).sort().join(“|”)`
