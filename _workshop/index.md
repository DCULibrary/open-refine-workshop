---
title: Intro to Data Cleaning with OpenRefine # The title of the page
date: 0000-01-01    # Page order is set by date
---

### What is Open Refine?
> A power tool for working with messy data

* More powerful than a spreadsheet
* More interactive and visual than scripting
* More experimental/playful than a database

_David Huynh, OpenRefine creator_

### What is messy data? And why should you clean it?

Data that needs cleaning is often called messy data - it is data that is inconsistent or poorly structured in some way.

Typically you’ll clean your data because you’re going to do something else with it. Maybe to visualise it or present it in some way, or to analyse or draw conclusions from it. Cleaning your data will help ensure any work or outputs based on the dataset is accurate and reliable.

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

| Institution	| Library | Address 1 | Town/City | Region | Postcode |
| ----------- | --------| --------- | --------- | ------ | ---------|
| University of Wales	| Llyfrgell Thomas Parry Library | Llanbadarn Fawr | Aberystwyth | Ceredigion | SY23 3AS |
| University of Aberdeen | Queen Mother Library | Meston Walk | Aberdeen | | AB24 3UE |
| University of Birmingham | Barnes Library | Medical School | Birmingham | West Midlands | B15 2TT |
| University of Warwick | Library | Gibbett Hill Road | Coventry | | CV4 7AL |
