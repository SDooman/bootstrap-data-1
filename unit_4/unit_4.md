# Unit 4

### Agenda:

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

 - What is the sum of elements in `l1`?
 - What is the sum of elements in `l2`?
 - What is the sum of elements in `l3`?

### Functions that consume lists of numbers
The **sum** is your first example of 
a function that consumes a list.  In previous
functions you have used, the arguments have 
been Numbers, Strings, or Booleans.


