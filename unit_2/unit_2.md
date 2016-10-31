# Unit 2

### Agenda:

### Product Outcomes:

Students begin using table manipulation
functions in Pyret.

### Standards and Evidence Statements: 

### Length: -Number- Minutes

### Glossary:

### Materials:

### Preparation:

## <a id="selecting"></a> Selecting

You've just loaded your first table into pyret: a 
table containing information about the Presidents
of the United States.  Now it's time to learn how 
you can do interesting things with this table.  Make
sure you've opened the Pyret program you wrote in Unit 1
for this section.  Add the code blocks given in this 
unit to your definitions window.

This table has 4 columns.  Some tables you'll encounter
may have hundreds of columns.  But what if we only want
to look at two of the columns?  There should be a way to
select the columns we care about, and discard the rest.

It turns out there is a way to do that: `select`!

The following code will make a new table using the 
old presidents data, by selecting the columns you 
specify:

```
name-and-party-table = select name, party from presidents-table end
```
The `select` expression will take the column names given (in this
case, `name, party`) from the specified table `presidents-table` 
and create a new table called name-and-party-table with just those columns.

### Exercise

## <a id="ordering"></a> Ordering

### Exercise
 - What does it mean when something is in alphabetical order?
 - Order these names alphabetically:  Ben, Abigail, John, Caroline..
 - Order these names in reverse alphabetical order:  Ben, Abigail, John, Caroline.
 - What does *ascending* mean?
 - What does *descending* mean?
 - Order these numbers so that they are *ascending*:  0, 3, 1, -2, 5.5
 - Order these numbers so that they are *descending*:  0, 3, 1, -2, 5.5

If you type `presidents-table` into the interactions window
and hit Enter, it will display the presidents of the USA starting with George Washington 
(in chronological order).  But what if we want to read the presidents
in the opposite order?

Pyret lets you change the order of a table's rows with the `order`
expression.  For example, the code below will create a table listing
the presidents in reverse chronological order:

```
reverse-chronological = order presidents-table:
  presidency descending
end
```

Here, presidents that have larger values in the **presidency**
column will be closer to the top, and presidents with smaller values 
in the **presidency** column will be closer to the bottom.  Ordering
is different from selecting in that ordering doesn't change/remove
any of the values within the rows:  for example, the row with
Barack Obama still has presidency value 44, party value "Democratic",
and home-state value "Illinois".

This command orders the table by numerical values in the presidency
column.  We can also order the table by string values: *ascending*
corresponds to alphabetical, and *descending* corresponds to
reverse alphabetical.

```
alphabetical-names = order presidents-table:
  name ascending
end
reverse-alphabetical-names = order presidents-table:
  name descending
end
```

### Exercise
 - Order the presidents-table by home state alphabetically (*ascending*)
 - Order the presidents-table by home state in reverse alphabetical order


