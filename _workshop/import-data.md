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

### Create your first OpenRefine project
Once OpenRefine is launched in your browser
* Click `Create Project` from the left hand menu
* Select `Web Addresses (URLs)`
* Enter `http://tiny.cc/dcuopenrefine` in the text box
* Click `Next >>`

OpenRefine will give you a preview of how it will parse your dataset. If you don't see anything in the preview it's because it has been unable to parse it correctly. There are various options of format types and how to generate the column titles.
The next screen (see below) gives you options to ensure the data is imported into OpenRefine correctly. The options vary depending on the type of data you are importing.

* Click in the `Character encoding` box and set it to `UTF-8`. This can be important if you have a dataset that uses certain special characters.
* Ensure the first row is used to create the column headings by checking the box `Parse next 1 line(s) as column headers` (this should already be checked)
* Make sure the `Parse cell text into numbers, dates, ...` box is not checked. We will work through this during the exercises.
* The `Project Name` box in the upper right corner will default to the title of your imported file. Click here and give your project a different name

Once you are happy click the `Create Project >>` button at the top right of the screen. This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.

#### Going Further
* Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.
* Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a `record path` i.e. the parts of the file that will form the data rows in the OpenRefine project.
