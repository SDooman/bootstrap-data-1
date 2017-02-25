# Unit 4: Table Manipulation Part 2

### Agenda:
 - [Intro](#intro)
 - [Sieving](#sieving)
 - [Extending](#extending)

### Product Outcomes:

Students continue learning table manipulation
expressions in Pyret.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:

 - **Sieving**:  Filtering rows out of a 
   table that don't satisfy a predicate
 - **Predicate**:  An expression, taking a 
   particular value from a row, which
   evalates to *true* if the row should 
   be kept in the new output table.
 - **Extending**:  Creating a table with 
   an entirely new column, created 
   by computing new values from the 
   old values in a row.
 - **Expression**: A combination of values
   that may have operators, which is used
   to compute new values.
 - **Operator**: A binary operator that
   has a lefthand side and a righthand
   side, and computes a new value using
   these two sides as input.  For example,
   `+`, `-`, `*`, `\`, `<`, `>` are all
   operators.

### Materials:
 - Google Drive
 - Editing Environment (Pyret Editor)

### Preparation:
 - Each student (or pair) has a Google account
 - Each student (or pair) has completed Unit 1

## <a id="intro"></a> Intro

So far you've learned how to use `order`
and `select` to produce new table objects
that can answer questions following the Order
pattern.  These were your first exposure to
ways of creating new tables, but none of 
these methods changed the values of entries
in the tables.  In this Unit, we're going to
use operations that will calculate new values
from the data in tables.

## <a id="sieving"></a> Filtering/Sieving

## Group Exercise

Let's look at our favorite 4th grade class
again.

Say you're the teacher, and you want to create
a new table that only has students who scored
less than an 85 on the test.  Which students
would be in this table?

### Teacher Notes
 - *Physically write the outline for this 
   new table on the board and have students 
   tell you what to put in each row.  Your
   outline should have the same number of columns,
   but a different number of rows.  Make sure 
   to have the students take notice of this;
   these new operations will change the dimensions
   of the table.*

In order to answer these questions, 
you're *filtering*.  *Filtering* means you're 
asking a true/false question about each piece 
of data in a list, and if the answer is true, you
keep the data.  Otherwise, you throw it out.  
In this exercise, the true/false question we are
asking is:  is a student's score lower than 85?
If it's true, we keep that student in our new 
table, otherwise that student is not in the new
table.

## Exercise
 - Turn to Unit 4 in your workbook and complete
   the filtering exercise.

In a filter, this true/false question you're asking 
is called a **predicate**. Predicates are 
always true/false questions.

Pyret allows filtering using the `sieve` expression.  
The following code generates a table with only foods
that have less than 600 calories

```
sieve nutrition using calories:
  calories < 600
end
```

Here, our predicate is the code `calories < 600`.  
For a particular row, if `calories < 600` is true, 
then we keep the row in the new table.  
Otherwise, we leave it out. 

Notice that we just introduced another new operator:
`<`.  `<` compares two things and gives true if the
left side is less than the right side.  It gives 
false otherwise.  Pyret has several such operators:
`>` for greater than, `==` for asking if the left
side is equal to the right side, `>=` for greater 
than or equal to, and `<=` for less than or equal
to.  We use these operators to write **expressions**.
An expression a combination of values (like the 
entry for a food item's number of calories) and an
operator (like the `<` operator).

The following code creates a new table with only
presidents in the "Whig" party:

```
sieve presidents using party:
  party == "Whig"
end
```

For each of the following exercises, 
write the code to create a table using `sieve`:

## Exercise
 - A table with every president who is from "Virginia".
   What is the predicate for this filter?
 - A table with every food with less than 15g of fat.
 - A table with every food with less than 15g of fat,
   but containing only *food, fat* columns and ordered
   by fat in ascending order.

## <a id="extending"></a> Extending

One of the most powerful things you can 
do with tables in Pyret is compute new values 
using the data from a table.  This is called 
**extending** a table, which is done with the 
keyword `extend`.  Extending lets us produce
new tables with values that are computed 
from columns from an old table.  
This involves using expressions, like we did 
with `sieve`, but in a slightly different way.

First, open your workbooks to Unit 4.  You'll
see a table that has two columns, and a third
column with only one value filled in.  It's your
job to fill in the correct values for each of 
the other entries.

The following code creates a new table that 
has the same columns as the `nutrition` table, 
plus a new column with the amount of calories 
*not* from fat:

```
extend nutrition using calories, calories-from-fat:
  fat-free-cals : calories - calories-from-fat
end
```

The line `extend nutrition-table using 
calories, calories-from-fat:` tells us which 
table is being extended, and which columns are 
being used to define the new column.  
The name of the new column is `fat-free-cals`, 
and it is defined by the expression
`calories - calories-from-fat`

## Exercise
 - Extend the presidents table to have a column called 
   `years-in-office` which is defined using the
   expression `end-year - start-year`
 - Select columns *name, years-in-office* from this table
   and order by *years-in-office* in descending order.
 - Which president served the most years in office?
 - Extend the nutrition table to have a column called
   `protein-density`, which is the amount of protein 
   in serving size (`protein / serving-size`)
 - Select columns *food, protein-density* from this table
   and order by *protein-density* in descending order.
 - Which food item has the highest protein density?

