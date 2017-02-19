# Unit 3 Workbook Answers

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
   `select name, eyes from animals end`

 - Write the code to select only the Name 
   and Legs columns from `animals`
   `select name, legs from animals end`

 - Draw the table this code produces:
   `select name, lifespan from animals end`

   | name       | lifespan |
   |------------|----------|
   | Human      | 71       |
   | Garden Ant | 8        |
   | Spider     | 2.5      |
   | Bear       | 10       |

 - What code produces this table?   
   | eyes |
   |------|
   | 2    |
   | 2    |
   | 8    |
   | 2    |

   `select eyes from animals end`

 - **CHALLENGE**:  Draw the table this code
   produces:
   ```
   select legs from
     select name, legs from animals end
   end
   ```

   | legs |
   |------|
   | 2    |
   | 6    |
   | 8    |
   | 4    |

