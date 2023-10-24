`Import necessary libraries`<br>
`Load dataset into program accessing dataset's path`<br>
`Print the dataset to see whether the data was imported correctly`<br>
`Define variable result as empty list`<br>
`Define variable keyword as user input`<br>
```
FOR row in dataset:
    IF keyword = keyword in keywords column
        Add article title in result
    ELSE 
        Continue
```
`Print result`<br>

`Set dataset to data/xml-dataset.xml`<br>
`If (dataset length is > 0)`<br>
`   Write "Enter search parameter:"`<br>
`   Read parameter`<br>
`   If (parameter is "year" or parameter is "keyword" or parameter is "author" or parameter is "year" or parameter is "language" or parameter is "type")`<br>
`      Write "Enter parameter value:"`<br>
`      Read value`<br>
`      If parameter is "year"`<br>
`         Read end`<br>
`      Set results as empty list`
`      If (parameter is "keyword")`<br>
`          Set count to 0`<br>
`          For record in dataset`<br>
`               For keyword in record.keywords`<br>
`             If (keyword contains value)`<br>
`                  Add record to results`<br>
`      If (parameter is "author")`<br>
`         For record in dataset`<br>
`              For author in record.authors`<br>
`                 If (record.authors contains value)`<br>
`                 Add record to results`<br>
`      If (parameter is "year)`<br>
`         For record in dataset`<br>
`             If (record.year is >= value and record.year is <= end)`<br>
`                 Add record to results`<br>
`      If (parameter is "language")`<br>
`         For record in dataset`<br>
`             If (record.language is value)`<br>
`                 Add record to results`<br>
`      If (parameter is "type")`<br>
`         For record in dataset`<br>
`         If (record.work-type is value)`<br>
`             Add record to results`<br>
`       If (results size is 0)`<br>
`           Write "No results."`<br>
`   Else write "Error: invalid parameter."`<br>
`Else write "Error: empty dataset."`
