---
title: Intro to Data Cleaning with OpenRefine # The title of the page
date: 0000-01-01    # Page order is set by date
---

### What is messy data? And why should you clean it?

Data that needs cleaning is often called _messy_ data. It is data that is inconsistent or poorly structured in some way.
This could be in relation to how it is formatted, where data appears, or in terminology used.

Typically you will look to clean your data because you’re going to do something else with it. Maybe to visualise it or present it in some way, or to analyse or draw conclusions from it. Cleaning your data will help ensure any work or outputs based on a given dataset is accurate and reliable. It is thus an important process for researchers to be aware of when using data in their research.

> _It is often said that 80% of data analysis is spent on the process of cleaning and preparing the data._  
> _Data preparation is not just a first step, but must be repeated many times over the course of analysis as new problems come to light or new data is collected._
>
> Hadley Wickham, [ _Tidy Data_ ](https://vita.had.co.nz/papers/tidy-data.pdf)

### What is OpenRefine?
> OpenRefine is:  
_*A power tool for working with messy data*_   
* More powerful than a spreadsheet
* More interactive and visual than scripting
* More experimental/playful than a database
>
> _David Huynh, OpenRefine creator_

OpenRefine is most useful for data in _tabular_ format, like a spreadsheet or csv file, or in standardised formats like json or xml. Broadly speaking, it enables you to:
- [x] detect instances of inconsistent or messy data
- [x] take steps to address those issues
- [x] link to external sources enhance your dataset further

Some common scenarios or objectives might be:

* you want to know how frequently a value appears
* you want to know how all values are distributed across a dataset
* you want to change all the dates in the list to a single common date format.

Quite often, you might not have clear objectives. And OpenRefine is good for that too! It lets you look at data in different ways and identify useful processes to clean or tidy your dataset (in the article above, Wickham talks about _tidy_ data as a subset of _clean_ data i.e. the part that is more concerned with structuring your data correctly in order to facilitate analysis.)

[//]: # (There can be a concern that it cleaning data may remove complexity and variations which are important in and of themselves. In their article [_Against Cleaning_](https://dhdebates.gc.cuny.edu/read/untitled-f2acf72c-a469-49d8-be35-67f9ac1e3a60/section/07154de9-4903-428e-9c61-7a92a6f22e51) Trevor Mu&#241;oz and Katie Lawson identify the term data _cleaning_ as problematic rather that the process itself which is (or should be) very much human-led. And that is true with OpenRefine: it is very useful software to bring things to the surface and find out if action is required for reliable analysis or visualisation, but the processes involved in data cleaning is transparent and controlled rather than automated.)

### Some examples

Dates may be in different formats:

| Data you have    | Desired Data |
| ---------------- | ------------ |
| 1st January 2014 | 2014-01-01   |
| 01/01/2014       | 2014-01-01   |
| Jan 1 2014       | 2014-01-01   |
| 2014-01-01       | 2014-01-01   |

Names of people or places may be misspelt or not capitalised:

| Data you have    | Desired Data |
| ---------------- | ------------ |
| London           | London       |
| London]          | London       |
| London,]         | London       |
| london           | London       |

Or you might have lots of information bundled together that you might want in a more granular layout.

For example, you may want to get from address data like this:

| Address in single field	|
| :---------------------- |
| University of Wales, Llyfrgell Thomas Parry Library, Llanbadarn Fawr, ABERYSTWYTH, Ceredigion, SY23 3AS |
| University of Aberdeen, Queen Mother Library, Meston Walk, ABERDEEN, AB24 3UE	|
| University of Birmingham, Barnes Library, Medical School, BIRMINGHAM, West Midlands, B15 2TT |
| University of Warwick, Library, Gibbett Hill Road, COVENTRY, CV4 7AL |

to something more like this:

| Institution	             | Library                        | Address 1         | Town/City   | Region        | Postcode |
| ------------------------ | ------------------------------ | ----------------- | ----------- | ------------- | ---------|
| University of Wales	     | Llyfrgell Thomas Parry Library | Llanbadarn Fawr   | Aberystwyth | Ceredigion    | SY23 3AS |
| University of Aberdeen   | Queen Mother Library           | Meston Walk       | Aberdeen    |               | AB24 3UE |
| University of Birmingham | Barnes Library                 | Medical School    | Birmingham  | West Midlands | B15 2TT  |
| University of Warwick    | Library                        | Gibbett Hill Road | Coventry    |               | CV4 7AL  |

As well as cleaning your data, OpenRefine can be used to _enhance_ your dataset. An example is if you have a list of names of people which can be linked to records in an external authority, and then related data pulled in from that data source.

| Data you have | Date of Birth from VIAF (Virtual Int. Authority File) | Date of Death from VIAF |
| ------------- | ----------------------------------------------------- | ----------------------- |
| Braddon, M. E. (Mary Elizabeth) |                                1835 |                    1915 |
| Rossetti, William Michael |                                      1829 |                    1919 |
| Prest, Thomas Peckett |                                          1810 |                    1879 |

### What Should I Know When Working With OpenRefine?
* OpenRefine runs in your browser but all data and processes are stored locally
* Any sharing of data or workflows is done via OpenRefine's export/import process
* You are NOT modifying original/raw data. OpenRefine works with a copy
