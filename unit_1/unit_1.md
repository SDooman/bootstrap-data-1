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
large data sets.

### Teacher Notes
 - Motivate importance of data science by 
   using examples that may relate to student
   interests.  Here are some examples:
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

| First Name | Last Name | Eye Color      | Height (inch) |
|------------|-----------|----------------|---------------|
| John       | Doe       | Green          | 52.0          |
| Jane       | Smith     | Brown          | 49.1          |
| Javon      | Jackson   | Brown          | 57.7          |
| Angela     | Enriquez  | Hazel          | 52.5          |
| Jack       | Thompson  | Blue           | 53.0          |
| Dominique  | Rodriguez | Hazel          | 51.1          |
| Sammy      | Carter    | Blue           | 56.2          |
| Andrea     | Garcia    | Brown          | 50.8          |

This is a table with information about 
students in a 4th grade class.  The 
information in a table is arranged 
into **rows** and **columns**.  In the 
example, each column has all the values 
for a certain **attribute** of a person.  
For example, the 3rd column contains 
the age of each person in the class.  
Here, the **attribute** is Age.

The very top row in this table is a 
special row:  Every value in the top row
is the name of an **attribute**.  
We call this the **header row**.  
Every other row in the table is called 
a **record**, and contains values for 
every **attribute** or **column**.  
In our example, each **record** represents
a person, and each value in the record 
is a person's Age, Favorite Food, etc.

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
 - What is the value of the "Number of Legs" 
   attribute for the Human record?

## <a id="importing"></a> Importing Data
Now that you know what tables are, 
it's time to use them.  There are many
different apps for working with tables, 
but the one we'll be using is Google Sheets.  
Google Sheets is a Spreadsheet software:  
a spreadsheet is a collection of sheets, 
and each sheet can hold tables. 

Each student (or pair of students) 
will follow these instructions.

Before using Sheets, we need to 
create the Pyret script that will 
load the table.  Go to 
[this link](https://code.pyret.org/) 
to create an empty Pyret program.  
If you've never signed into Pyret before,
it will ask you for a Google account.  
Upon signing in, Pyret will create 
folders for you in your Google drive.
All of the Pyret scripts you write 
will be saved into the **code.pyret.org** 
folder.  Save this blank program 
as `intro`.

Go to [this link](https://drive.google.com/) 
once you've saved your program.  
You should see several folders, 
one of which is called **code.pyret.org**.  
Double click on this folder to 
navigate to it.  When we create our 
spreadsheet, it should be in this 
folder so that Pyret can access it.

Now, open [this link](https://gsuite.google.com/learning-center/products/sheets/get-started/#section-1-2)
and follow the instructions to Import 
and convert old spreadsheets to Sheets.  

Make sure to use the **presidents.csv** 
file, and to follow these instructions 
within the **code.pyret.org** folder 
in your drive, which should be 
open in the other tab.

After finishing these instructions, 
call the teacher over to check your work.
You should be able to see the presidents
data set, which has six columns: 
Presidency, Name, Party, Home State,
Year Started and Year Ended.

## <a id="loading"></a> Loading Tables

Now that you know the basic information
about tables, it's time to get some 
hands on experience with tables in 
Pyret.  If you haven't used Pyret before,
Pyret is a programming language that 
is used in several Bootstrap curriculums,
One of the best parts of Pyret is that
you can create and load tables from
Google Sheets, which is Google's 
Spreadsheet software.

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

First, we'll need to import Pyret's 
library for interacting with files 
in the Google Drive.  Add each of 
the following lines of code to your
definitions window (the left window):

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
presidents = load-table: presidency, name, party, home-state, year-started, year-ended
  source: presidents-sheet.sheet-by-name("presidents", true)
end
```

Now, hit run then type `presidents` into
the interactions window (the right window).


## <a id="loading"></a> Loading Tables
Now that you've imported a table, 
it's time to use it with Pyret.
Go back to your empty program, and 
add each snippet of code below to your 
definitions window (the editor on the left).

First, we'll need to import Pyret's 
library for interacting with files 
in the Google Drive:

`import gdrive-sheets as GDS`

Next, we add the line of code that 
accesses our new Google Spreadsheet:

`presidents-sheet = GDS.my-spreadsheet("presidents.csv")`

Finally, we add the code to load 
this spreadsheet into 
the form of a Pyret table:

```
presidents-table = load-table: presidency, name, party, home-state
  source: presidents-sheet.sheet-by-name("presidents.csv", true)
end
```

Now run your code, and type 
`presidents-table` into the interactions
window.  If all goes well, you'll 
see the first few entries of your new 
table in the interactions window (the 
editor on the right).

You can use the function `GDS.my-spreadsheet` 
to load any spreadsheet that is in 
your **code.pyret.org** folder.
But you can also load a spreadsheet 
from *anyone's* google drive, 
as long as it's public:

The following code will load 
a table from a Sheet that we've
created, and you can use it 
in your own Pyret programs:

```
nutrtion-sheet = GDS.load-spreadsheet("1YXOMMSdpKwsiGzFE8SY7LJXEvuAHNBzw1RgJYuxSvZc")

nutrition-table = load-table: food, serving-size, calories, calories-from-fat, total-fat, sat-fat, trans-fat, cholesterol, sodium, carbs, fiber, sugar, protein
  source: nutrition-sheet.sheet-by-name("nutrition", true)
end
```

Now run your code and type `nutrition-table` 
into the interactions window.  You 
should see the entries in a table 
containing nutrition information 
about menu items at a restaurant.

## <a id="closing"></a> Closing

Congratulations!  You've just finished 
loading your first table
in Pyret, which is a big accomplishment.  

