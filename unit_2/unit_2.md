# Unit 2

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
 - **Categorical Data**: Data that can
   only have a certain number of values.
 - **Quantitative Data**: Numerical 
   data that measures an amount.

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

## <a id="categorical"></a> Categorical Data

Let's look again at the very first 
example of a table from Unit 1:

| First Name | Last Name | Hair Color     | Height (inches) |
|------------|-----------|----------------|-----------------|
| John       | Doe       | Blonde         | 52.0            |
| Jane       | Smith     | Brown          | 49.1            |
| Javon      | Jackson   | Black          | 57.7            |
| Angela     | Enriquez  | Black          | 52.5            |
| Jack       | Thompson  | Red            | 53.0            |
| Dominique  | Rodriguez | Brown          | 51.1            |
| Sammy      | Carter    | Blonde         | 56.2            |
| Andrea     | Garcia    | Black          | 50.8            |

The first kind of data we'll look
at is **categorical** data.  If a 
column contains **categorical** data,
each value can only be one of a few
choices (also called categories).

Let's think about hair color for a second.
How many different hair colors are there
without hair dye?

*Guide students towards this list:
Blonde, Brown, Black, Red, White, Grey.*

So if there are only 6 different natural
hair colors, then each value in the column
has to be one of these categories.  Here,
Hair Color is a **categorical** variable,
which means that the column contains
**categorical** data.

## <a id="quantitative"></a> Quantitative Data

Now look at the Height (inches) column.  
How many possible values are there for
an entry in this column?  In other words,
is there a fixed number of categories 
of height that a student could have?

Height is **quantitative** data:  there 
is no fixed number of values that an
entry in the table could have.
The main difference between 
**quantitative** and **categorical**
data is that **quantitative** 
data can be less than or more than
other values of **quantitative** data.
In other words, **quantitative** data
measures the *amount* of something; it
quantifies something.

For example, Sammy Carter has height
56.2 and John Doe has height 52.0, which
means Sammy Carter is taller than John
Doe, because she has more height.  Notice
how for Hair Color (**categorical**) 
can't be compared this way; the question
"is blonde more than brown" doesn't make
any sense.

### Exercise:

Open your [google drive](https://drive.google.com)
and open the `intro` file which has the
first two tables you've loaded into Pyret.

 - Look at the Presidents table again.
   Does the state column have **categorical**
   or **quantitative** data?  If it is
   **categorical**, how many categories
   are there?
 - In the nutrition table, does the 
   calories column have **categorical**
   or **quantitative** data?  How can
   you tell?

## <a id="difference"></a> Rules of Thumb

Knowing the difference between **categorical**
and **quantitative** is an important
part of data analysis, because (as you will
see in the next couple units) there
are different ways to learn from & visualize
these two kinds of data.

If you are ever trying to figure out if
data is **categorical** or **quantitative**,
ask yourself: "How many choices are there 
for a value?".  If you can count this number,
the data is categorical.  Otherwise, ask
"Is this value measuring the amount of 
something?"  If it is, it's quantitative.

