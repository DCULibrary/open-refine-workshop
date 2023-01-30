---
title: Intro to Data Cleaning with OpenRefine # The title of the page
nav: Intro to OpenRefine
date: 0000-01-01    # Page order is set by date
---
![OpenRefineLogo](https://upload.wikimedia.org/wikipedia/commons/b/bd/OpenRefine_logo_%282018-present%29.svg)

## What is OpenRefine?
> *A power tool for working with messy data*   
* More powerful than a spreadsheet
* More interactive and visual than scripting
* More experimental/playful than a database
>
> _David Huynh, OpenRefine creator_

OpenRefine is a free, open-source Java application. You can download it from <http://openrefine.org/download.html>.

It is most useful where data is already in _tabular_ format like a spreadsheet or csv file, or in standardised formats like json or xml. Moving that data into OpenRefine enables you to:
1. detect instances of inconsistent or messy data
2. take steps to address those issues
3. enhance your data by linking to external sources

Or you might not have any clear idea in advance of what you want or need to do. OpenRefine is very useful there too, for exploring a dataset and identify what might be useful next steps.

[//]: # (There can be a concern that it cleaning data may remove complexity and variations which are important in and of themselves. In their article [_Against Cleaning_](https://dhdebates.gc.cuny.edu/read/untitled-f2acf72c-a469-49d8-be35-67f9ac1e3a60/section/07154de9-4903-428e-9c61-7a92a6f22e51) Trevor Mu&#241;oz and Katie Lawson identify the term data _cleaning_ as problematic rather that the process itself which is (or should be) very much human-led. And that is true with OpenRefine: it is very useful software to bring things to the surface and find out if action is required for reliable analysis or visualisation, but the processes involved in data cleaning is transparent and controlled rather than automated.)

## What is messy data? And why should you clean it?

Data that needs cleaning is often called _messy_ data. It is data that is inconsistent or poorly structured in some way. This could be in relation to how it is formatted, where data appears, or in terminology used.

Typically you will look to clean your data because you’re going to do something else with it. Maybe to visualise it or present it in some way, or to analyse or draw conclusions from it. Cleaning your data will help ensure any work or outputs based on a given dataset is accurate and reliable. It is thus an important process for researchers to be aware of when using data in their research.

> _It is often said that 80% of data analysis is spent on the process of cleaning and preparing the data._  
> _Data preparation is not just a first step, but must be repeated many times over the course of analysis as new problems come to light or new data is collected._
>
> _Hadley Wickham,_ [ _Tidy Data_ ](https://vita.had.co.nz/papers/tidy-data.pdf)

So while you are usually cleaning data as a preparatory step, it’s very often a big part of any data-reliant project. And unfortunately it’s not something you do at the start and then skip off with your gleaming data. It’s an iterative process. But that can also be kind of a relief that you don’t have to "complete" your data cleaning.

### Some examples of messy data

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

Information bundled together that you might want in a more granular layout. For example, you may want to get from address data like this:

| Address |
| ------- |
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

### Tidy Data

The last example above where data is *restructured* relates to _**tidy data**_. This can be thought of as a subset of clean data, more concerned with structuring your data correctly. Hadley Wickham has written a really good introduction to this topic.
[![Tidy Data article screengrab](assets/images/TidyDataArticle.png)](https://vita.had.co.nz/papers/tidy-data.pdf)

> *“Tidy datasets are easy to manipulate, model and visualise, and have a specific structure:*
> - *each variable is a column, *
> - *each observation is a row, and *
> - *each type of observational unit is a table.”*
> *Hadley Wickham, [Tidy Data](https://vita.had.co.nz/papers/tidy-data.pdf)*

In the same article, Wickham writes
> *"“It is often said that 80% of data analysis is spent on the process of cleaning and preparing the data.*
> *Data preparation is not just a first step, but must be repeated many times over the course of analysis as new problems come to light or new data is collected.”*

### Data Types

![Image of Data and Lore from Star Trek](assets/images/ManyTypesOfData.png)

...But mostly in OpenRefine we work with tabular data. This can be in different formats - excel, csv file or xml file but in structure it is *tabular*. And when we talk about *messy* data we are talking about the values in those cells in those tables. Blank cells, duplicates, errors. Data types also relates to how OpenRefine treats numbers, strings etc. - we'll look more at that later.

### Enhancing your Data

As well as cleaning messy data, OpenRefine can be used to _enhance_ your dataset. For example, if you have a list of names of people which can be linked to records in an external authority, related data can then be pulled in from that data source.

| Data you have | Date of Birth from VIAF (Virtual Int. Authority File) | Date of Death from VIAF |
| ------------- | ----------------------------------------------------- | ----------------------- |
| Braddon, M. E. (Mary Elizabeth) |                                1835 |                    1915 |
| Rossetti, William Michael |                                      1829 |                    1919 |
| Prest, Thomas Peckett |                                          1810 |                    1879 |

## Other reasons to use OpenRefine

- It is important to **know what you *did* to your data**. Journals and granting agencies are increasingly requiring documentation of this. With OpenRefine, you can easily capture all of this and share it as supplemental material.
- All actions are **easily reversed** in OpenRefine.
- OpenRefine always uses a copy of your data and **does not modify your original dataset**.
- OpenRefine always **keeps your data private** on your own computer until you choose to share it. It works by running a small server on your computer and using your web browser to interact with it, but your private data never leaves your computer unless you want it to.

---------------

## 💡 OpenRefine helps you...

✅ **Clean** - Find and fix inconsistency with faceting, clustering, cell transforms

✅ **Transform** - change formats, restructure, split/join multi-valued cells, split columns, transpose columns/rows

✅ **Extend** - enrich data by combining files, merging projects, fetching URLs, reconciliation with online databases…

✅ **Automate** - reuse your processing routine by exporting operation history in JSON!