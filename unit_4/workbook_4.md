# Unit 3 Workbook

## Page 1

Below is a table bound to the id `animals`

| name       | legs | eyes | lifespan |
|------------|------|------|----------|
| Human      | 2    | 2    | 71       |
| Garden Ant | 6    | 2    | 8        |
| Spider     | 8    | 8    | 2.5      |
| Bear       | 4    | 2    | 10       |

 - Write the code to select only the Name 
   and Eyes columns from `animals`
   _______________________________

 - Write the code to select only the Name 
   and Legs columns from `animals`
   _______________________________

 - Draw the table this code produces:
   `select name, lifespan from animals end` 

 - What code produces this table?
   
   | eyes |
   |------|
   | 2    |
   | 2    |
   | 8    |
   | 2    |

 - **CHALLENGE**:  Draw the table this code
   produces:
   ```
   select legs from
     select name, legs from animals end
   end
   ```

