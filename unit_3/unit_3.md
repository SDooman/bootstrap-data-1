# Unit 3

### Agenda:
 - [Sieving](#sieving)
 - [Extending](#extending)

### Product Outcomes:

Students continue learning table manipulation
expressions in Pyret.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:

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

## <a id="sieving"></a> Sieving

So far you've learned how to select specific columns, and re-order rows.
Next we'll learn how to make new tables using specific rows.

## Group Exercise
 - Which of these numbers are greater than 0?  [1, 0, 2, -1, 4, -3]
 - Which of these strings are longer than 4 characters?  "hi", "hey", "hello" "greetings"
 - Which of these strings come before "Pizza" alphabetically?  "Apple", "Bacon", "Toast", "Salad"

In order to answer these questions, you're  *filtering*.  
*Filtering* means you're asking a true/false question
about each piece of data in a list, and if the answer is true, you
keep the data.  Otherwise, you throw it out.  In the first exercise,
the question is "is this number greater than 0?".  In the second,
the question is "is this string longer than 4 characters".

## Group Exercise
 - What is the question being asked in the third exercise?

In a filter, this question you're asking is called a **predicate**.
Predicates are always true/false questions.

Pyret allows filtering using the `sieve` expression.  
The following code generates a table with only foods
that have less than 600 calories

```
less-600-cals = sieve nutrition-table using calories:
  calories < 600
end
```

Here, our predicate is the code `calories < 600`.  For a
particular row, if `calories < 600` is true, then we keep
the row in the new table.  Otherwise, we leave it out. 

The following code creates a new table with only
presidents in the "Whig" party:

```
whig-presidents = sieve presidents-table using party:
  party == "Whig"
end
```

For each of the following exercises, write the code to create
a table using `sieve`:

## Exercise
 - A table with every president who is from "Virginia".
 - A table with every food with less than 15g of fat.
 - Select only *food, fat* from the table above, and
   order it by fat in ascending order.

## <a id="extending"></a> Extending

One of the most powerful things you can do with tables is
compute new values using the data from a table.  This is
called **extending** a table, which is done with the 
keyword `extend`.

The following code creates a new table that has the same
columns as the nutrition-table, plus a new column with the
amount of calories *not* from fat:

```
cals-not-from-fat = extend nutrition-table using calories, calories-from-fat:
  calories-not-from-fat : calories - calories-from-fat
end
```
The line `extend nutrition-table using calories, calories-from-fat:`
tells us which table is being extended, and which columns are 
being used to define the new column.  The name of the new column
is `calories-not-from-fat`, and it is defined by the expression
`calories - calories-from-fat`

## Exercise
 - Extend the presidents table to have a column called 
   `years-in-office` which is `end-year - start-year`
 - Select columns *name, years-in-office* from this table
   and order by *years-in-office* in descending order.
 - Extend the nutrition table to have a column called
   `protein-density`, which is the amount of protein 
   in serving size (`protein / serving-size`)
 - Select columns *name, protein-density* from this table
   and order by *protein-density* in ascending order.

