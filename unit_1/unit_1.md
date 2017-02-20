# Unit 1:  Tools for Data

### Agenda:
 - [Introduction](#intro)
 - [What are Tables?](#tables)
 - [Tables in Google Sheets](#sheets)
 - [Loading Tables](#loading)
 - [Closing](#closing)

### Product Outcomes:

Students import and create their own Google Sheets,
and load these Sheets into Pyret as Tables.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:

 - **Spreadsheet**:  A Google Spreadsheets 
   document.  Contains one or more Sheets.
 - **Sheet**:  A Sheet containing tabular 
   data within a Spreadsheet.
 - **Table**:  Data arranged into rows 
   and columns.
 - **Entry**:  One value in a table.
 - **Row**:  A collection of entries in a
   table all along the same horizontal line.
 - **Column**:  A collection of entries in 
   a table that are all along the same 
   vertical line, and are of the same type.
 - **Header Row**:  The first row in a table, 
   which contains the names of each attribute 
   of a record.
 - **Record**:  A row that is not a header 
   row (any other row in the table).
 - **Attribute**:  The name of a particular column,
   which is found in the header row.
 - **Pyret Table**:  An object in Pyret 
   that represents a Table.
 - **Load**:  To create a Table in Pyret from 
   tabular data in a Sheet.

### Materials:
 - Google Drive 
 - Editing Environment (Pyret Editor)

### Preparation:
 - Computer for each student (or pair)
 - Each student has Google account

## <a id="intro"></a> Introduction
Welcome to Bootstrap Data Science Lite.  
In this course, you'll learn how to ask 
and answer questions about data.  
The process of learning from data is 
called data science.  Data science techniques 
are used by scientists, business people, 
politicians, sports analysts, and hundereds of other 
different fields to ask and answer questions 
about data.

In order to ask questions from data, you 
will use a programming language.  Just like
any language (English, Spanish, French), programming
languages have their own vocabulary and grammar that
you will need to learn.  The language you'll
be learning for data science is Pyret, which 
lets you ask and answer questions quickly from very 
large data sets.  The first feature in Pyret you 
will learn to use for data science is the data
table.  But first, you need to know what tables are.

### Teacher Notes
 - *Motivate importance of data science by 
   using examples that may relate to student
   interests.  Here are some examples:*
 - - Pop Culture:
 - - - [Emojis](http://motherboard.vice.com/read/a-data-scientists-emoji-guide-to-kanye-west-and-taylor-swift)
 - - - [Pop Music](https://mic.com/articles/131092/these-students-are-using-data-science-to-predict-which-rap-songs-will-become-hits#.0d3wkhxQE)
 - - Politics:
 - - - [Elections](http://www.kdnuggets.com/2016/06/politics-analytics-trump-clinton-sanders-twitter-sentiment.html)
 - - - [Polls](http://fivethirtyeight.com/)
 - - Sports:
 - - - [Predicting Seasons](http://games.espn.com/fba/tools/projections)
 - - Sciences (there's a lot out there for this one)
 - - - [Environment](http://www.salon.com/2015/07/18/how_big_data_can_help_save_the_environment_partner/)
 - Set expectations and rules for the class:
   This is only an introduction to data science,
   so some more complicated questions may not 
   be answered.

## <a id="tables"></a> What are Tables?
Let's start with an example:

![Basic Table](/unit_1/img/table_basic.png)

This is a **table** storing information
about students in a 4th grade class.

![Entry Highlighted](/unit_1/img/table_entry.png)

**Tables** are collections of **entries**.
Each **entry** contains a value, which is
usually a Number or a String of characters.
The values stored in table entries are almost
always related to each other in some way
(which is why tables are often called 
relational data).

Table entries are organized into **columns**
and **rows**.

![Column Highlighted](/unit_1/img/table_column.png)

All of the **entries** in a particular 
**column** will contain values that are 
the same type, and represent the same thing.
For example, each value in the 3rd column 
represents the age of a person in the class.
In this example, age is an **attribute**.
An **attribute** is just the name of what
each value in a column is representing.

![Header Highlighted](/unit_1/img/table_header.png)

The first **row** in a table is a special
row called the **header row**.  Each **entry**
in the **header row** is the name of
the **attribute** for a particular column.

![Row Highlighted](/unit_1/img/table_row.png)

Every other row in the table is called 
a **record**, and contains values for 
every **attribute** or **column**.  
In our example, each **record** represents
a person, and each entry in the record 
is a person's First Name, Last Name, etc.

### Exercise
Turn to page 1 in your workbook,
and complete the exercise to identify
different aspects about the table 
containing information about different
species of animal.   

### Teacher Notes
 - *Show the kids slides with each 
   image of the example table, focusing
   on the different aspects of tables*
 - *Instill a sense in kids that records
   represent distinct objects, and each
   entry in a record represents an 
   attribute of that object.*

## <a id="sheets"></a> Tables in Google Sheets
Now that you know what tables are, 
it's time to use them.  There are many
different apps for working with tables, 
but the one we'll be using is Google Sheets.  
Google Sheets is an app that lets you 
create and edit **spreadsheets**:  
a spreadsheet is a collection of sheets, 
and each sheet can hold a table. 

### Exercise

Open your web browsers, and navigate to
the following link:

[https://docs.google.com/spreadsheets/d/14er5Mh443Lb5SIFxXZHdAnLCuQZaA8O6qtgGlibQuEg/edit?usp=sharing](https://docs.google.com/spreadsheets/d/14er5Mh443Lb5SIFxXZHdAnLCuQZaA8O6qtgGlibQuEg/edit?usp=sharing)

This Google Sheet contains a table 
with information about the presidents
of the United States.

Now turn to Page 2 in your workbooks
and complete the exercise answering
questions about the presidents table.  

## <a id="loading"></a> Loading Tables

Now that you know the basic information
about tables, it's time to get some 
hands on experience with tables in 
Pyret.  One of the best parts of Pyret 
is that you can create and load tables 
from Google Sheets.  Later in the course
we'll use Pyret to compute different 
values from the data to answer complex
questions about the data.

### Exercise

First, we need to create the Pyret 
script that will load the table.  Go to 
[this link](https://code.pyret.org/) 
to create an empty Pyret program.

If you've never signed into Pyret before,
it will ask you for a Google account.  
Upon signing in, Pyret will create 
folders for you in your Google drive.
All of the Pyret scripts you write 
will be saved into the **code.pyret.org** 
folder.  Save this blank program 
as `unit-1`.

If you *have* programmed in Pyret 
before, you can skip to the next paragraph.
The Pyret editor has two windows that
you can write code into:  the definitions 
window (on the left), and the interactions 
window (on the right).  The definitions 
window is where you write longer, multi
line programs, and then run them with the
**Run** button.  The interactions window
is where you can write short programs and 
quickly run them by hitting enter.

Add each of the following lines of code 
to your definitions window (the left 
window). Don't worry if you don't understand
what the code is doing, it will be
explained in more detail later in
the unit.  First, we'll need to import 
Pyret's library for interacting with files 
in the Google Drive:

`import gdrive-sheets as GDS`

Next, we add the line of code that 
accesses a specific Google Spreadsheet.
This code will access the Google Sheet 
at [this url](https://docs.google.com/spreadsheets/d/14er5Mh443Lb5SIFxXZHdAnLCuQZaA8O6qtgGlibQuEg/edit#gid=0)

`presidents-sheet = GDS.load-spreadsheet("14er5Mh443Lb5SIFxXZHdAnLCuQZaA8O6qtgGlibQuEg")`

Finally, we add the code to load 
this spreadsheet into 
the form of a Pyret table:

```
presidents = load-table: nth, name, home-state, year-started, year-ended, party
  source: presidents-sheet.sheet-by-name("presidents", true)
end
```

Now, hit run then type `presidents` into
the interactions window (the right window).
You should see the same presidents table that
was in the Google Sheets document.

Next, we will load a different table that
you haven't seen before.  This table will
contain nutrition information for a 
restaurant menu.

Add the code to load access this Google
Sheet:

`nutrition-sheet = GDS.load-spreadsheet("1fMNIgAZ-wdNF7sf4j5Vns-g2Qr9UDa8kSgnzxPfDl5I")`

Next, add the code to load this spreadsheet into
the form of a Pyret table.  Notice that this 
table has several more columns than the 
presidents table.

```
nutrition = load-table: food, serving-size, calories, calories-from-fat, fat, cholesterol, sodium, sugar, protein
  source: nutrition-sheet.sheet-by-name("nutrition", true)
end
```
Now, hit run again then type `nutrition`
into the interactions window.  You should
see a table with 10 records containing
information about different foods.

### Teacher Notes
 - *If you would like to substitute a different
    data set for this activity, please reference
    Supplemental Unit 3, or Unit 1 specific
    instructions on loading and importing a 
    custom data set*.
 - *Common sources of trouble for students 
    loading this data include not getting 
    the source URL strings exactly correct.*

## <a id="closing"></a> Closing

Congratulations!  You've just finished 
loading your first table
in Pyret, which is a big accomplishment.  
Next, you will learn how to write Pyret
code that manipulates these tables.  This
will be the first thing in your "data science
tool box".

