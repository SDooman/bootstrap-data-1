# Unit 4

### Agenda:
 - [Lists](#lists)
 - [Calculations From Lists](#math-list-funs)
 - [Extracting Lists From Tables](#extract)

### Product Outcomes:

Students are introduced to lists as
ordered collections of data.  They 
learn to extract lists from tables
and calculate relevant values from 
lists (sum, min, max).

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:
 - **Lists**:  An ordered collection of data, which
   can be of any type.
 - **Element**:  An entry in the list.
 - **Sum**:  For a list containing only numbers,
   the total value of all elements added together.
 - **Minimum**:  For a list containing only numbers,
   the smallest value of all the elements.
 - **Maximum**:  For a list containing only numbers,
   the largest value of all the elements.
 - **Extract**:  A keyword that converts a particular
   column of a table into a list.
 
### Materials:

### Preparation:
 - Each student (or pair) has a Google account

## <a id="lists"></a> Introduction to Lists

So far you've used Tables as a way to store
data.  Today, you'll learn a different way
to store data in Pyret:  lists.

Lists are ordered collections of data.  Here is
an example of a list in Pyret:

```
[list: 1, "Arr", true]
```

This list contains 3 values:  a Number with value 1,
a String with value "Arr", and a Boolean with value true.

For this Unit, we will only be looking at lists that 
contain only numbers, but it is important for you to 
know that lists can have elements with different types.

## <a id="math-list-funs"></a> Calculating Values From Lists
### Group Exercise

The **sum** of a list of numbers is the number you
get when you add every element of the list together.

The **minimum** of a list of numbers is the smallest
number in that list.

The **maximum** of a list of numbers is the largest
number in that list.

```
l1 = [list: 1, 2, 3]
l2 = [list: -1, 1, 2]
l3 = [list: 0.2, 0.6, 1.2, 2.9]
```

 - What is the sum of elements in `l1`?  What are the min & max?
 - What is the sum of elements in `l2`? What are the min & max?
 - What is the sum of elements in `l3`? What are the min & max?

Pyret has functions for calculating each of these values
in the `math` package.  Here is how to use them:

```
import math as m
my-list = [list: -1, 2, 3.5, 4.5]
a = m.sum(my-list) # a is equal to 9
b = m.min(my-list) # b is equal to -1
c = m.max(my-list) # c is equal to 4.5
```

In previous functions you have used, the 
arguments have been Numbers, Strings, or 
Booleans. These are your first examples of 
functions that consume an argument of
type List.

### Exercise

Answer the following questions about these lists
by adding code in your definitions window:

```
list-1 = [list: 1, 8, 99, 2, 14, 3]
list-2 = [list: 0.2, -0.4, 0.1, 0.8, -0.12, 1]
list-3 = [list: 0, 1, 0, 1, "0", 1]
```

 - Let id `k` be the maximum of `list-1`
 - Let id `diff` be the difference between 
   the minimum and maximum of `list-2`.
 - Try to calculate the minimum of `list-3`.
   Why does this not work?

After completing this exercise, the value for
`k` should be 99, and the value for `diff`
should be `1.4`.  Calculating minimum of `list-3`
raises a type error because `list-3` has a String
value as an element, and the `min` function
expects arguments of lists containing only numbers.

Remember, this unit only focuses on functions
that take lists of numbers as arguments.  We can
write functions that take any kind of list
later, but for now we will only look at functions
that take lists of numbers.

## <a id="extract"></a> Extracting Lists from Tables

One of the most powerful aspects of Pyret is that 
it lets you **extract** columns as lists from tables!
This lets you take *real data* from tables, and
perform computations like **sum, minimum, and maximum**
on the data in the list.

Below is a table bound to the id `animals`:

| name       | legs | eyes | lifespan |
|------------|------|------|----------|
| Human      | 2    | 2    | 71       |
| Garden Ant | 6    | 2    | 8        |
| Spider     | 8    | 8    | 2.5      |
| Bear       | 4    | 2    | 10       |

This code will extract the `eyes` column into a list,
then calculate the maximum number of eyes a particular
kind of animal has.

```
import math as m
eyes-list = extract eyes from animals end
max-eyes = m.max(eyes-list)
```

### Group Exercise
 - How would you extract the lifespan column as a list?
 - Using the list of lifespan values, how would you 
   calculate the animal with the shortest lifespan?



### Exercise 
