# Unit 5:  Measuring Center

### Agenda:

### Product Outcomes:

### Standards and Evidence Statements: 

### Length: -60- Minutes

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

It not be impossible, we just need to ask 
a better question.  If we have two data
sets, with dog heights and human heights,
we need to ask:  is there a height that
is most representative of dogs?  Another
way to ask that is, out of all values 
a dog could have as its height, what is
roughly the "center" of those values?
We should ask the same thing for the humans 
too.  Then, by comparing the "centers" of these
two data sets, we can represent the general
difference in height between the two species.

This idea of a representative value, or
a "center" of a data set is very important
in statistics, and you will definitely
see it a lot if you go on to study subjects
that use data.  If you don't understand yet
what we mean by center, that's totally fine.
There are several ways to try and estimate
the "center" of a data set, and we will
learn each of these.  You may be familiar
with one or all of them already.

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
To find the **median** of a data set, we sort the
list and take the middle element.

*When going through examples on the board, a
useful strategy for finding the "middle" element
of the sorted lists is to cross off numbers on
both ends of the list until there is only 1 or 2
elements uncrossed.  Encourage the students to 
use this cross-out strategy in the exercises*

```
[list: 1, 3, 2, 7, 6, 5, 9]
```

In this example, the sorted list is `[list: 1, 2, 3, 5, 6, 7, 9]`
There are 7 elements total, so we take the 4th element
as the **median**:  Therefore the **median** of this list is 5.

For lists that have an even number of elements, there are
technically 2 middle elements.  In this case, the median is 
just the **average** of those two numbers.

```
[list: 5, 2, 1, 3]
```

In this example, the sorted list is `[list: 1, 2, 3, 5]`.
There are 4 elements in total, so the **median** is the
average of the 2nd and 3rd elements, which is 1.5

### Exercise

```
l4 = [list: -1, 2, -1, 3, 4]
l5 = [list: 1.2, 0.4, 0.8, 1.3]
```

 - What is the **median** of `l4`?
 - What is the **median** of `l5`?

## <a id="mode"></a> Mode

The last measurement of the "center" of a data set 
that we will learn is the **mode**.  The **mode** of a data
set is the element in the set that appears the most
often.

```
[list: 1, 1, 2, 2, 2]
```

In this list, 1 appears twice, and 2 appears 3 times.
This means that 2 is the **mode** of this data set.
Sometimes, a data set will have more than one **mode**.
For example, this list has two modes:

```
[list: 0, 1, 2, 2, 3, 4, 4, 5]
```

### Group Exercise

```
l6 = [list: -1, -1, 0, 1, 3]
l7 = [list: 1.1, 1.1, 1.2, 1.2, 1.4]
l8 = [list: 1, 2, 3, 4]
```

 - What is the **mode** of `l6`?
 - What is the **mode** of `l7`?
 - What is the **mode** of `l8`?

## <a id="pyret"></a> Mean, Median & Mode in Pyret

Now that you know what **mean**, **median**, and 
**mode** are, it's time to use Pyret to calculate
these values for data sets.

In pairs, create a new Pyret program
and add the following code to your 
definitions window:

```
import statistics as s

l = [list: 1, 1, 2, 3]
l-mean = s.mean(l)
l-median = s.median(l)
l-mode = s.mode(l)

other-list = [list: 0, 0, 1, 1, 2]
other-list-modes = s.modes(other-list)
```

The statistics package contains all of
the functions you'll use to calculate
mean, median, and mode.  Notice that 
there are two functions for mode:
Just regular `mode` will give a single
value, wheras `modes` gives a list
of values.  This is important because
sometimes lists will have more than
one mode.  If you only want to worry
about one mode, then you can just
use `mode`.

Now that you know how to use 
these functions in Pyret, it's time 
to use them on actual data!  We're going
to look at data from a classroom:  A 
teacher has recorded students' grades
for 3 different tests.  They want to 
figure out if students' grades are getting
better overall.

In groups of two, answer the exercise questions
after creating a new Pyret program with
the following code added to the definitions
window:

```
import gdrive-sheets as GDS
grades-sheet = GDS.load-spreadsheet("1wDtmlt--ewos2fvUy9XF2si5s4lTHVGil3IlPA0GXHU")
```

 - Load the grades table (it has 4 columns:
   `student`, `test1`, `test2`, and `test3`)
 - What are the mean, median and mode of `test1`?
 - What are the mean, median and mode of `test2`?
 - What are the mean, median and mode of `test3`?
 - Are student grades increasing?  Why or why not?

