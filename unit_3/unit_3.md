# Unit 3: Table Manipulation Part 1

### Agenda:
 - [Selecting](#selecting)
 - [Ordering](#ordering)
 - [Ordering in Pyret](#pyret-order)
 - [Combining Table Expressions](#combining)

### Product Outcomes:

Students begin using table manipulation
expressions in Pyret.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:
 - **Data Story**: A story told that
   is driven by questions asked/answered
   using data.
 - **Pattern**: A particular kind of 
   question that can be answered by many
   different data sets that all have 
   a certain property.
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
[//]: # (TODO: This intro to data stories needs work)

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

Let's look again at our favorite 4th 
grade class.  This time, we have 3 
columns:  First name, Last name, and 
the students' grades on the most recent test:

![Basic Table](/unit_3/img/basic_table.png)

### Group Exercise
 - Who has the highest score on the test?
 - What are the first names of the top 4
   scorers on the test?

When we answer this question, we have to look
through every row in the table to figure out
what the top 4 scores are, then the names 
of the students with those scores.  The
next operation we will see is **ordering**.
**Ordering** is sorting all of the rows in a 
table in a meaningful way, using one of the columns
in particular.  Data scientists will often **order**
tables so that they are easier to search through.

### Group Exercise
 - Create a new table with these same
   students as rows, but the rows
   are ordered by test scores in descending
   order.

### Teacher Notes
 - Have the students tell you what to write
   in each cell of the new table.  Make them
   explain why certain information should 
   stay in the same row as others (i.e. 'Jane' 
   and 'Smith' stay in the same row since 
   they belong to the same person).

![Test Grade DESC](/unit_3/img/test_grade_desc.png)

This table we just created is the classroom table
**ordered** by test grade in **descending** order.
It is in **descending order** by test grade because
the test grades start high at the top of the table,
and get lower further in the table.

This next table is in **ascending order** by test
grade, because the values in the test grade column
start low, and get larger further in the table.

![Test Grade ASC](/unit_3/img/test_grade_asc.png)

Data scientists don't just **order** tables by columns
with numbers in them:  tables can be **ordered** by
Strings too.  Here's the classroom table in 
**descending order** by the first name column.

![First Name DESC](/unit_3/img/first_name_desc.png)

### Group Exercise
 - What do you notice about this table?

This new table is the classroom table in 
**alphabetical order** by the first name column.
Data scientists treat **alphabetical order** to
be **ascending** order for Strings.   

### Group Exercise
 - What would the classroom table look like in
   **reverse alphabetical order**?

### Teacher Notes
 - No need to redraw the entire new table, just
   have students describe how it would be different;
   namely, all of the rows from the **alphabetically
   ordered** table would be in the opposite order

A table that is in **reverse alphabetical order**
is in **descending** order.

![First Name DESC](/unit_3/img/first_name_desc.png)

Open your workbook and complete Page 1 of Unit 3.

## <a id="pyret-order"></a> Ordering in Pyret

Pyret lets you change the order of a
table's rows with the `order` expression.  
For example, the code below will 
create a table listing the foods by the 
value in the sodium column in **descending order**:

```
order nutrition:
  sodium descending
end
```

Here, foods that have larger values 
in the **sodium** column will be closer 
to the top, and foods with smaller values 
in the **sodium** column will be closer 
to the bottom.  

To **order** the table by a column with
Strings, we use the same keywords `descending`
or `ascending`.  The following code will order
the `presidents` table by the presidents 
first names **alphabetically**

```
order presidents-table:
  name ascending
end
```

### Exercise
 - Can we order the `presidents` table by the
   presidents' last names?  Why not?
 - The column `nth` contains a number representing
   the chronological order of the presidents (i.e.
   George Washington is the 1st president so the 
   value of George Washington's `nth` column is 1.
   Order the presidents table by the nth column
   in **ascending** order.  What are the political
   parties of the first 5 presidents?

 - Order the nutrition-table by the protein values, 
   in **descending order**.  What are the 3 foods with
   the highest amount of protein?

Notice how similar these two questions.  Both
of them involve ordering the table by a column X
to figure out which rows have the highest/lowest
value for X.  With this new ordered table, it's 
easy to see the top 5 presidents, or the top 3 proteiny
foods.

[//]: # TODO: Rename Order Pattern to something better

This is the first example of a **pattern**, which we
will call the **Order Pattern**.

## <a id="combining"></a> Combining Table Expressions

The technique of using `order` to search for 
attributes of the highest/lowest rows according
to a particular column is very powerful.  This
technique is even more powerful when you combine
`order` with `select`!  

The following code orders each [name, home-state] 
pair from `presidents` by name in reverse 
alphabetical order:

```
select name, home-state from
  order presidents:
    name descending
  end
end
```

### Exercise
 - Select **food, serving-size** 
   from `nutrition`, and order
   the table by **food** in ascending order
 - Select **name, party**  from 
   `presidents`, and order 
   the table by **party** in descending order

