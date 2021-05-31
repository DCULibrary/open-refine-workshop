---
title: Layout and Basic Functions     # The title of the page
date: 0000-01-04    # Page order is set by date
---

### Layout of OpenRefine
OpenRefine displays data in a tabular format. Each row will usually represent a ‘record’ in the data, while each column represents a type of information. This is similar to how you might view data in a spreadsheet or a database. As with a spreadsheet, the individual bits of data live in ‘cells’ at the intersection of a row and a column.

#### Working with data in OpenRefine
* OpenRefine only displays a limited number of rows of data at one time. You can adjust the number choosing between 5, 10 (the default), 25 and 50 at the top left of the table of data.
* That’s because you’re not supposed to be working with your data record by record; we’ll find ways to group it into batches and then work with it in those batches through column menus.
* We will use the drop down menus at the top of the data columns. When you select an option in a particular column (e.g. to make a change to the data), it will affect all the cells in that column. If you want to make changes across several columns, you do this one column at a time.

#### Rows and Records
OpenRefine has two modes of viewing data: ‘Rows’ and ‘Records’. It defaults to Rows mode, where each row represents a single record in the data set - in this case, an article. In Records mode, OpenRefine can link together multiple rows as belonging to the same Record.

#### How can I move my data into OpenRefine?
There are a number of ways to get data into Refine:
* select a file in a local directory or that you have downloaded
* by url if a dataset is hosted on the web (this is the method we wil use)
* copy/paste directly (in some text format like csv or json)

We will do it by uploading a file from a url <http://tiny.cc/dcuopenrefine>. This is taken from the __[*Carpentries*](https://carpentries.org)__ OpenRefine lessons, which this lesson is based on (see credits).

### Create your first OpenRefine project
Once OpenRefine is launched in your browser:
* Click `Create Project` from the left hand menu
* Select `Web Addresses (URLs)`
* Enter `http://tiny.cc/dcuopenrefine` in the text box
* Click `Next >>`

OpenRefine should give you a preview of how it will parse your dataset and gives various options to ensure the data is imported into OpenRefine correctly. The exact options vary depending on the type of data you are importing. For this exercise we'll make a few checks:

* Click in the `Character encoding` box and set it to `UTF-8`. This can be important if you have a dataset that uses certain special characters.
* Ensure the first row is used to create the column headings by checking the box `Parse next 1 line(s) as column headers` (this should already be checked)
* Make sure the `Parse cell text into numbers, dates, ...` box is not checked. We will work through this during the exercises.
* The `Project Name` box in the upper right corner will default to the title of your imported file. Click here and give your project a different name

Once you are happy click the `Create Project >>` button at the top right of the screen. This will create the project and open it for you. Projects are saved as you work on them, there is no need to save copies as you go along.

#### Going Further
* Look at the other options on the Import screen - try changing some of these options and see how that changes the Preview and how the data appears after import.
* Do you have access to JSON or XML data? If so the first stage of the import process will prompt you to select a `record path` i.e. the parts of the file that will form the data rows in the OpenRefine project.
