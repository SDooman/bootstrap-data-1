# Unit 3: Table Manipulation Part 1

### Agenda:
 - [Selecting](#selecting)
 - [Ordering](#ordering)
 - [Combining Table Expressions](#combining)

### Product Outcomes:

Students begin using table manipulation
expressions in Pyret.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:

 - **Selecting**:  Creating a new table 
   using only some of the columns from 
   a different table.
 - **Ordering**:  Sorting the rows of a 
   table by values in a column.
 - **Ascending**:  An order increasing in value.
 - **Descending**:  An order decreasing in value.
   evalates to *True* if the row should be kept 
   in the new output table.  by computing new 
   values from the old values in a row.

### Materials:
 - Google Drive
 - Editing Environment (Pyret Editor)

### Preparation:
 - Each student (or pair) has a Google account
 - Each student (or pair) has completed Unit 1

## <a id="intro"></a> Introduction
[//] # (TODO: This intro to data stories needs work)

So far you have seen how tables are used to 
store information.  But if all data science
was about was storing data, this class would 
be boring!  This Unit will be your first 
exposure to telling a *Data Story*.

A *Data Story* is a story you tell using data!
By asking and answering questions using data 
tables, we can learn any number of things about
that data.  When you, the data scientist, 
present what you've learned by asking and answering
questions, you are telling a story about the data.
For example, in professional sports, scouts will
collect data on how fast, strong, tall, accurate,
etc. each player is, and ask questions from that 
data.  When they decide which players to draft,
they're telling a story about the data and which
players were the answers to their questions.

So we're going to be creating and telling 
*Data Stories*.  How do we do that?

Each *Data Story* starts by asking questions.
These questions can be answered using specific
data science/statistics techniques.  Another
important aspect of these questions is that 
they usually follow a certain **pattern**.  No
matter whether a data scientist is working with
sports data, crime rates, movie information,
the questions they ask will follow a **pattern**.

In this course, we will teach you some of the
most important question **patterns** that show up in
data science, and you will ask and answer these
kinds of questions with a data set of your choice.
Once you've answered these questions, you can 
tell your own data story!  For this Unit, you
will learn the first two Table operations that 
help you ask/answer the first **pattern** of 
questions.

## <a id="selecting"></a> Selecting

You've just loaded your first tables
into Pyret; Now it's time to learn how 
you can do interesting things with these 
tables.  Make sure you've opened the `unit-1` 
Pyret program you wrote in Unit 1 for this 
section.  Save a new version of this file
as `unit-3`, and add each of the code blocks given 
in this unit to your definitions window.

The presidents table has 4 columns.  
The nutrition table has 13, and you have 
to scroll to the right to see all of the 
columns.  Some tables you'll encounter will 
have many more than 13 columns.  But what 
if we only want to look at two of the 
columns in a table?  There should 
be a way to select the columns we care about, 
and discard the rest.

It turns out there is a way to do that: `select`

```
select name, party from presidents-table end
```

The `select` expression will take the column
names given (in this case, `name, party`) 
from the specified table `presidents-table` 
and create a new table with just those columns.

The following code will select only the `food`, 
`calories` columns from the nutrition table:

```
select food, calories from nutrition-table end
```

Turn to Unit 3 in your workbook and complete
the exercises on Page 1.  

### Teacher Notes
 - *When demonstrating the `select` operation,
    it may be helpful to do "live coding", by
    projecting a screen where you write the code
    and display the output of the interactions
    window to the class*
 - *The benefits of using the `select` operation
    are mostly for the human:  having less columns
    does not make it significantly faster to perform
    operations on the table, but less columns does
    make it easier for humans to observe relations
    between columns (like in the examples above).
    
    `select` will be used in combination with `order`
    (and other operations later in the course) to produce 
    tables that are easier for humans 
    to visually extract relevant information from,
    so one exercise that could highlight these benefits
    is having students race (everyone tries to beat a 
    time of 3 seconds) to find the 3 foods with highest
    protein amount, or what parties Herbert Hoover,
    Benjamin Harrison, and Millard Fillmore belong to.*

### Exercise
 - In your Pyret program, add code to your 
   definitions window that creates
   a new table called `name-and-home` that 
   selects the name and home state columns 
   from `presidents`
 - Add code to your definitions window that 
   creates a new table called `food-and-fat` 
   that selects the food and fat columns
   from `nutrition`

### Teacher Notes
 - *Encourage students to experiment writing
   code in the interactions window, then once
   they are satisfied that the expressions 
   satisfy the problem, have students bind
   those expressions to identifiers in the
   definitions window.

## <a id="ordering"></a> Ordering



### Group Exercise
 - What does it mean when something 
   is in alphabetical order?
 - Order these names alphabetically:  
   Ben, Abigail, John, Caroline.
 - Order these names in reverse alphabetical 
   order:  Ben, Abigail, John, Caroline.
 - What does *ascending* mean?
 - What does *descending* mean?
 - Order these numbers so that they 
   are *ascending*:  0, 3, 1, -2, 5.5
 - Order these numbers so that they are 
   *descending*:  0, 3, 1, -2, 5.5

If you type `presidents-table` into 
the interactions window and hit Enter, 
it will display the presidents of the USA 
starting with George Washington (in 
chronological order).  But what if we want 
to read the presidents in the opposite order?

When a table is ordered, it's easier 
to search for particular values.  For example,
it's way easier to find the food with
the highest **sodium** value it the 
`nutrition-table` is in
descending order by **sodium**.

Pyret lets you change the order of a
table's rows with the `order` expression.  
For example, the code below will 
create a table listing the foods by **sodium** 
value in descending order:

```
sodium-ordered = order nutrition-table:
  sodium descending
end
```

Here, foods that have larger values 
in the **sodium** column will be closer 
to the top, and foods with smaller values 
in the **sodium** column will be closer 
to the bottom.  Ordering is different 
from selecting in that ordering doesn't 
change/remove any of the values within the 
rows:  for example, the row for Hamburger still 
has a serving sice of 98g, has 240 calories, etc.

This command orders the table by 
numerical values in the sodium
column.  We can also order the table 
by string values: *ascending*
corresponds to alphabetical, and *descending* 
corresponds to reverse alphabetical.  The 
following code creates two tables; one
that orders the presidents by name alphabetically, 
and another that orders the presidents 
in reverse alphabetical order.

```
alphabetical-names = order presidents-table:
  name ascending
end

reverse-alphabetical-names = order presidents-table:
  name descending
end
```

Add the above code to your definitions 
window, run the code, then
type `alphabetical-names` and 
`reverse-alphabetical-names` into
the interactions window.

### Exercise
 - Order the presidents-table by home state alphabetically (**ascending**)
 - Order the presidents-table by home state in reverse alphabetical order
 - Order the nutrition-table by the protein values, in ascending order

## <a id="combining"></a> Combining Table Expressions

Order and Select are even more useful 
when you can combine them!
The following code orders each [name, home-state] 
pair from `presidents-table` by name 
in reverse alphabetical order:

```
name-home-state = select name, home-state from presidents-table end
name-state-ordered = order name-home-state:
  name descending
end
```

### Exercise
 - Select **name, serving-size** 
   from `nutrition-table`, and order
   the table by **name** in ascending order
 - Select **name, party**  from 
   `presidents-table`, and order 
   the table by **party** in descending order

