# Unit 5:  Measuring Center

### Agenda:

### Product Outcomes:

### Standards and Evidence Statements: 

### Length: -Number- Minutes

### Glossary:

### Materials:

### Preparation:

## <a id="intro"></a> Varying Data

So far in this course you have seen
how to ask for the `min`, `max`, and
`sum` of a list of numbers.  In the context
of the menu, this is great for finding
things like the menu item with the lowest
amount of carbohydrates, or the highest
sodium.

But now, imagine we had two different 
data sets:  one list containing the heights
of many different dogs, and another containing
the heights of many different humans.  We want
to know the answer to this question:  are dogs
taller than humans?

*Actually ask the students this question.  Most
should say that humans are taller.  Provide 
counter examples (great dane is taller than most
elementary school students;  Zeus the great 
dane was 3 ft 8, taller than many kids in elementary
school!).  If any say dogs are taller, bring 
up a tall human (i.e. Sultan Kösen, world tallest man).*

It seems we can come up with examples for
both dogs being taller than humans, and humans are
taller than dogs.  So it is impossible to say that
all humans are taller than dogs, or that all dogs are
taller than humans.  So is the question "are dogs taller
than humans" impossible to answer?

*Try to get a student to say that "most of the time,
humans are taller than dog".*

It not be impossible.  

## TODO(Sam):  Articulate that we want to estimate the center

## <a id="mean"></a> Mean

The first way to measure the center of a data set is 
called the **mean**.  You may have heard the term
**average** before;  these are two names for the
same thing.  The **mean** (sometimes called arithmetic
mean) is defined as follows:

The sum of all numbers in the list, divided by the 
size of the list.

For example, here is how to calculate the **mean** of
the following list:

```
[list: 1, 1.2, 1.8, 2]
sum = 1 + 1.2 + 1.8 + 2 # Add all of the elements
mean = sum / 4 # Divide by number of elements
```

The mean of this list is `1.5`.

### Group Exercise

```
l1 = [list: 1, 3, 5]
l2 = [list: -1, 1, -0.5, 1, 1]
l3 = [list: 4, 4, 4, 4, 5, 5, 5, 5, 36]
```

 - What is the **mean** of `l1`?
 - What is the **mean** of `l2`?
 - What is the **mean** of `l3`?

## <a id="median"></a> Median

Lets look at the last example.  Imagine this
list represents the ages of the people in a 
kindergarten class:  it includes the 8 students,
and the teacher.  The arithmetic mean of this list 
is `9`.  But 9 seem like the "center" of the list?

This is an example of where the **mean** is not
necessarily the best representative of the center,
because nobody in the classroom is actually 9 
years old.

Another value we can calculate is the **median**.
To find the **median** of a data set

## <a id="mode"></a> Mode

The third and final measurement of the "center" of
a data set is the **mode**.  The **mode** of a data
set is the element in the set that appears the most
often.

```
[list: 1, 1, 2, 2, 2]
```

In this list, 1 appears twice, and 2 appears 3 times.
This means that 2 is the **mode** of this data set.

## <a id="pyret"></a> Mean, Median & Mode in Pyret

