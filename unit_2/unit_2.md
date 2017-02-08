# Unit 2: Introduction to Data

### Agenda:
 - [Classifying Data](#classifying)
 - [Categorical Data](#categorical)
 - [Quantitative Data](#quantitative)
 - [Rules of Thumb](#difference)

### Product Outcomes:

Students learn to differentiate 
categorical and quantitative data.

### Standards and Evidence Statements: 

### Length: 45 Minutes

### Glossary:
 - **Quantitative Data**: Numerical data
   that measures an amount. Quantitative 
   data can meaningfully be added or 
   subtracted from other Quantitative
   data of the same kind, or compared 
   with less than/greater than other
   Quantitative data of the same kind.
   
 - **Categorical Data**: Data that can
   only have a certain number of values.
   Unlike Quantitative Data, Categorical
   Data cannot be compared meaningfully 
   with addition, subtraction, less than,
   or greater than.

### Materials:
 - Google Drive
 - Editing Environment (Pyret Editor)

### Preparation:
 - Computer for each student (or pair)
 - Each student has google account

## <a id="classifying"></a> Classifying Data

You have loaded your first tables into
Pyret.  These tables contain different 
data:  the first is a table about 
the presidents of the US, and the 
second has nutritional information
about items on a menu.  Before we can
dive into all of the cool things you
can do with tables, we need to understand
the two different kinds of data that 
can appear in tables: **categorical** and
**quantitative**.

## <a id="quantitative"></a> Quantitative Data

Let's look again at the very first 
example of a table from Unit 1:

![Basic Table](/unit_2/img/table_basic.png)

The first kind of data we will look at is
**Quantitative Data**.  **Quantitative Data**
always measures an amount of something.  If
a question asks "how much" there is of something,
the answer will be quantitative data.

Look at the Height (inches) column.  
If you ask the question "How tall is John Doe?"
(in other words, how much height does John Doe
have?), the answer is 52.0 inches.  **Quantitative
Data** usually has units of measurement;
in this case the unit of measurement is inches.

Another important fact is that **Quantitative Data**
can be larger or smaller than other **Quantitative Data**.
For example, if we ask the question "Is John Doe
taller than Andrea Garcia?" (in other words, does John
Doe have more height than Andrea Garcia), it can
be answered by comparing their entries in the height
column.  John Doe's height is bigger than Andrea Garcia's,
so we can say yes, he is taller.

## <a id="categorical"></a> Categorical Data

Now look at the Eye Color column.

![Basic Table](/unit_2/img/table_basic.png)

Can we ask the question "Does John Doe have 
more eye color than Andrea Garcia?"  No.
That question makes no sense.  The second
kind of data we will look at is **Categorical
Data**.  We used **Quantitative Data** to quantify;
to ask "how much" there is of something.  **Categorical
Data** is used to categorize;  it puts something
into a category.  In this case, students
are put into the same category if they have
the same eye color.

Let's think about eye color for a second.
How many different eye colors are there?

*Guide students towards this list:
Amber, Blue, Green, Brown, Grey, Hazel.*

So if there are only 6 different natural
eye colors, then each value in the column
has to be one of these categories.  We would
say that this column has 6 different possible
categories.
 
### Exercise:

Open your [google drive](https://drive.google.com)
and open the `unit-1` file which has the
first two tables you've loaded into Pyret.  Then
turn to page 3 and answer the questions about 
these two data sets.

## <a id="difference"></a> Rules of Thumb

Knowing the difference between **categorical**
and **quantitative** is an important
part of data analysis, because (as you will
see in the next couple units) there
are different ways to learn from & visualize
these two kinds of data.

If you are ever trying to figure out if
data is **categorical** or **quantitative**,
ask yourself: is this data measuring an
amount of something? Does it make sense to
add/subtract values in this column?  If yes, 
then it is **quantitative**.  Otherwise, 
it's **categorical**.

If a column contains numbers, it is usually
quantitative, but not always!  For example,
a column containing zip codes is **categorical**,
because zip codes are not measuring an amount of
anything.

### Teacher's Notes
 - *Quantitative data may be continuous (no
   fixed number of possible values) or discrete
   (a fixed number of values).  For example, 
   a column containing scores for a test with
   two questions has 3 possible values: 0, 50, 
   or 100.  However, this is still quantitative
   and not categorical because the values are 
   measuring an amount (the amount of correctness)*
