# Unit 1:  Tools for Data

### Agenda:
 - [Introduction](#intro)
 - [What are Tables?](#tables)
 - [Importing Data](#importing)
 - [Loading Tables](#loading)
 - [Closing](#closing)

### Product Outcomes:

Students import and create their own Google Sheets,
and load these Sheets into Pyret as Tables.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:

 - **Spreadsheet**:  A Google Spreadsheets document.  Contains one or more Sheets.
 - **Sheet**:  A Sheet containing tabular data within a Spreadsheet.
 - **Table**:  Data arranged into rows and columns.
 - **Row**:  A single item in the table.
 - **Column**:  A set of values of a certain type in a table.
 - **Header Row**:  The first row in a table, which contains the names of each attribute of a record.
 - **Record**:  A row that is not a header row (an entry in the table).
 - **Attribute**:  The name of a particular column.
 - **Pyret Table**:  An object in Pyret that represents a Table.
 - **Import**:  To put data from an existing file into a Sheet.
 - **Load**:  To create a Table in Pyret from tabular data in a Sheet.

### Materials:
 - Google Drive 
 - Demo CSV File
 - Editing Environment (Pyret Editor)

### Preparation:
 - Computer for each student (or pair)
 - Each student has Google account
 - Demo CSV is loaded onto each computer

## <a id="intro"></a> Introduction
Welcome to Bootstrap Data 1!  In this course, you will learn about
Tables:  a widely used way of arranging data.  Almost every website
you have ever seen uses tables in the form of databases. By learning
how to use tables, you'll be able to ask and answer questions using
almost any kind of data you can find!

## <a id="tables"></a> What are Tables?
Let's start with an example:

| First Name | Last Name | Age | Grade | Favorite Class | Favorite Food |
|------------|-----------|-----|-------|----------------|---------------|
| John       | Doe       | 8   | 4     | Math           | Pizza         |
| Jane       | Smith     | 9   | 4     | Art            | Tacos         |
| Javon      | Jackson   | 8   | 4     | Recess         | Pizza         |
| Angela     | Enriquez  | 8   | 4     | Science        | Cake          |
| Anthony    | Thompson  | 9   | 4     | Recess         | Pasta         |
| Dominique  | Rodriguez | 8   | 4     | History        | Hamburgers    |

This is a table with information about students in a 4th grade class.
The information in a table is arranged into **rows** and **columns**.
In the example, each column has all the values for a certain **attribute**
of a person.  For example, the 3rd column contains the age of
each person in the class.  Here, the **attribute** is Age.

The very top row in this table is a special row:  Every value in the top row
is the name of an **attribute**.  We call this the **header row**.  Every
other row in the table is called a **record**, and contains values for 
every **attribute** or **column**.  In our example, each **record** represents
a person, and each value in the record is a person's Age, Favorite Food, etc.

### Exercise:

| Animal | Number of Legs |
|--------|----------------|
| Human  | 2              |
| Ant    | 6              |
| Spider | 8              |
| Bear   | 4              |  

 - How many rows does this table have?
 - How many columns does this table have?
 - What are the attributes in the header row?
 - What is the value of the "Number of Legs" attribute for the Human record?

## <a id="importing"></a> Importing Data
Now that you know what tables are, it's time to use them.  There are many
different apps for working with tables, but the one we'll be using is
Google Sheets.  Google Sheets is a Spreadsheet software:  a spreadsheet
is a collection of sheets, and each sheet can hold tables. 

Each student (or pair of students) will follow these instructions.

Before using Sheets, we need to create the Pyret script
that will load the table.  Go to 
[this link](https://code.pyret.org/) to create an empty
Pyret program.  If you've never signed into Pyret before,
it will ask you for a Google account.  Upon signing in,
Pyret will create folders for you in your Google drive.
All of the Pyret scripts you write will be saved into
the **code.pyret.org** folder.  Save this blank program as
**intro**.

Go to [this link](https://drive.google.com/) once you've 
saved your program.  You should see several folders, one
of which is called **code.pyret.org**.  Double click on 
this folder to navigate to it.  When we create our spreadsheet,
it should be in this folder so that Pyret can access it.

Now, open [this link](https://gsuite.google.com/learning-center/products/sheets/get-started/#section-1-2)
in a new tab, and follow instructions 2-5 in
 Section 1.2:  Import and convert old spreadsheets to Sheets.  
Make sure to use the **presidents.csv** file, and to follow
these instructions within the **code.pyret.org** folder in your
drive, which should be open in the other tab.

After finishing these instructions, call the teacher over to
check your work.

## <a id="loading"></a> Loading Tables
Now that you've imported a table, it's time to use it with Pyret.

Go back to your empty program, and add each snippet of code
below to your definitions window (the editor on the left).:

First, we'll need to import Pyret's library for interacting
with files in the Google Drive:

`import gdrive-sheets as GDS`

Next, we add the line of code that accesses our new
Google Spreadsheet:

`presidents-sheet = GDS.my-spreadsheet("presidents.csv")`

Finally, we add the code to load this spreadsheet into 
the form of a Pyret table:

```
presidents-table = load-table: presidency, name, party, home-state
  source: presidents-sheet.sheet-by-name("presidents.csv", true)
end

presidents-table
```

Now run your code.  If all goes well, you'll see the first 10
entries of your new table in the interactions window (the 
editor on the right).

## <a id="closing"></a> Closing

Congratulations!  You've just finished loading your first table
in Pyret, which is a big accomplishment.  Next, you'll learn
how to ask and answer questions using this data.

