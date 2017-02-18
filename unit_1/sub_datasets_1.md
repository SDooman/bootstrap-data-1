# Unit 1:  Loading Your Own Data

In order to substitute your own data
into this curriculum, the first step is
to import your data set into Google Drive.
After doing so, you can load any data
set from your Google Drive into Pyret.
Following these instructions is a prerequisite
for substituting your own data into the curriculum
for Unit 2 through Unit 10.  There is significant
overlap between this material and the Supplemental
Unit 3.

## Importing and Loading

 1.  First, import your data into Google Sheets.  If 
     you have never used/imported data into Google Sheets,
     use this link as a reference: [importing data into Google Sheets](https://support.google.com/docs/answer/40608?hl=en)
 2.  Make your Google Sheet public:  This means that
     you and all of your students can view/load this 
     table.  Follow [these instructions](https://support.google.com/docs/answer/2494822#link_sharing)
     to allow anyone with the link to your Google Sheet
     to view the data.
 3.  Examine the URL.  It should match this format:*
     https://docs.google.com/spreadsheets/d/**XXX**/edit#gid=Y
     Here, the portion marked **XXX** is a unique ID for the
     Google Sheets containing your data.  Copy the string marked 
     by **XXX**.
 4.  Create your empty Pyret file as directed in Unit 1
     and add the code to import the `gdrive-sheets` library.
     In the line of code defining `president-sheet`, replace
     the input string with your copied string for your own
     Google Sheet.  You should also rename this id from
     `president-sheet` to something that is more appropriate
     for your data.  EXAMPLE: if your data set is a table 
     with information about a school, rename the id to
     `school-sheet`.
 5.  Navigate back to your Google Sheet and look for a header
     row.  If there is a header row, make sure each of the
     column names make sense to you for this data.  If there
     is not a header row, write down a name for each column
     that makes sense to you*.  Additionally, look in the
     bottom left corner for the name of the particular Sheet
     containing your data.  In the default Google Sheets 
     document, it should be *Sheet1*, but this will change
     to the name of the file that was imported.  Rename this
     to *MySheet*.
 6.  In the line of code that creates the Presidents table, 
     replace each of the column names with the unique column names 
     of your data.  
 7.  Change the source parameter from `nutrition-sheet` to 
     the new name of your sheet.  
 8.  Change the string "presidents" to be "MySheet" in
     the first argument position of the `sheet-by-name`
     function.
 9.  If your table contains a header row, keep the second 
     argument of the `sheet-by-name` function as `true`.
     If your table does not contain a header row, change
     this argument to `false`.
 10. Finally, change the name of this table from `presidents`
     to something more appropriate.  EXAMPLE: if the data
     table contains information about a school, name this
     id to `school`.
 11. Type `school` into your interactions window.  If you
     get an error message saying the specified spreadsheet
     was not found, check to make sure your permissions are
     open, and that you copied the unique Google Sheets ID
     exactly right.

