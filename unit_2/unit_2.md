# Unit 2

### Agenda:

### Product Outcomes:

Students begin using table manipulation
functions in Pyret.

### Standards and Evidence Statements: 

### Length: 90 Minutes

### Glossary:

 - **Selecting**:  Creating a new table using only some of the
   columns from a different table.
 - **Ordering**:  Sorting the rows of a table by values in a column.
 - **Ascending**:  An order increasing in value.
 - **Descending**:  An order decreasing in value.
 - **Sieving**:  Filtering rows out of a table that don't satisfy a predicate
 - **Predicate**:  An expression, taking a particular value from a row, which
   evalates to *True* if the row should be kept in the new output table.
 - **Extending**:  Creating a table with an entirely new column, created 
   by computing new values from the old values in a row.

### Materials:
 - Google Drive
 - Editing Environment (Pyret Editor)

### Preparation:
 - Each student (or pair) has a Google account
 - Each student (or pair) has completed Unit 1

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

It turns out there is a way to do that: `select`

```
name-and-party-table = select name, party from presidents-table end
```
The `select` expression will take the column names given (in this
case, `name, party`) from the specified table `presidents-table` 
and create a new table called name-and-party-table with just those columns.

### Exercise

Below is a table called `animals`

| name       | legs | eyes | lifespan |
|------------|------|------|----------|
| Human      | 2    | 2    | 71       |
| Garden Ant | 6    | 2    | 8        |
| Spider     | 8    | 8    | 2.5      |
| Bear       | 4    | 2    | 10       |

 - Write the code to select only the Name and Eyes columns from `animals`
 - Write the code to select only the Name and Legs columns from `animals`
 - Write the code to select only the Name and Lifespan columns from `animals`

### Exercise
 - In your Pyret program, add code to your definitions window that creates
   a new table called `name-and-home` that selects the name and home state
   columns from `presidents-table`

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

## <a id="sieving"></a> Sieving

So far you've learned how to select specific columns, and re-order rows.
Next we'll learn how to make new tables using specific rows.

## Exercise
 - Which of these numbers are greater than 0?  [1, 0, 2, -1, 4, -3]
 - Which of these strings are longer than 4 characters?  "hi", "hey", "hello" "greetings"
 - Which of these strings come before "Pizza" alphabetically?  "Apple", "Bacon", "Toast", "Salad"

In order to answer these questions, you're doing something
called **filtering**.  **Filtering** means you're asking a true/false question
about each piece of data in a list, and if the answer is true, you
keep the data.  Otherwise, you throw it out.  In the first exercise,
the question is "is this number greater than 0?".  In the second,
the question is "is this string longer than 4 characters".

## Exercise
 - What is the question being asked in the third exercise?

In a filter, this question you're asking is called a **predicate**.
Predicates are always true/false questions.

Pyret allows filtering using the `sieve` expression.  
The following code creates a new table with only the first 5 presidents:

```
first-five-presidents = sieve presidents using presidency:
  presidency <= 5
end
```

Here, our predicate is the code `presidency <= 5`.  For a particular row,
if `presidency <= 5` is true, then we keep the row in the new table.
Otherwise, we leave it out.



## <a id="extending"></a> Extending

# TODO(Sam):  Add column for starting year and ending year to Presidents dataset, add exercises 
