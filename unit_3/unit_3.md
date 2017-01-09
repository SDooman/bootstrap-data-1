# Unit 3

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

 - **Selecting**:  Creating a new table using only some of the
   columns from a different table.
 - **Ordering**:  Sorting the rows of a table by values in a column.
 - **Ascending**:  An order increasing in value.
 - **Descending**:  An order decreasing in value.
   evalates to *True* if the row should be kept in the new output table.
   by computing new values from the old values in a row.

### Materials:
 - Google Drive
 - Editing Environment (Pyret Editor)

### Preparation:
 - Each student (or pair) has a Google account
 - Each student (or pair) has completed Unit 1

## <a id="selecting"></a> Selecting

You've just loaded your first tables
into pyret: a table containing information 
about the Presidents of the United States, 
and a table containing nutrional information 
for menu items.  Now it's time to learn how 
you can do interesting things with these 
tables.  Make sure you've opened the `intro` 
Pyret program you wrote in Unit 1 for this 
section.  Add each of the code blocks given 
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
name-and-party-table = select name, party from presidents-table end
```

The `select` expression will take the column
names given (in this case, `name, party`) 
from the specified table `presidents-table` 
and create a new table called 
name-and-party-table with just those columns.

The following code will select only the `name`, 
`calories` columns from the nutrition table:

```
name-and-calories-table = select name, calories from nutrition-table end
```

### Group Exercise

Below is a table bound to the id `animals`

| name       | legs | eyes | lifespan |
|------------|------|------|----------|
| Human      | 2    | 2    | 71       |
| Garden Ant | 6    | 2    | 8        |
| Spider     | 8    | 8    | 2.5      |
| Bear       | 4    | 2    | 10       |

 - Write the code to select only the Name 
   and Eyes columns from `animals`
 - Write the code to select only the Name 
   and Legs columns from `animals`
 - Write the code to select only the Name 
   and Lifespan columns from `animals`

### Exercise
 - In your Pyret program, add code to your 
   definitions window that creates
   a new table called `name-and-home` that 
   selects the name and home state columns 
   from `presidents-table`
 - Add code to your definitions window that 
   creates a new table called `name-and-fats` 
   that selects *name, total-fat, sat-fat, 
   trans-fat* from `nutrition-table`

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

