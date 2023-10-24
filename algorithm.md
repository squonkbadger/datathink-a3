`Set dataset to data/xml-dataset.xml`<br>
`If (dataset length is > 0)`<br>
`   Write "Enter search parameter:"`<br>
`   Read parameter`<br>
`   If (parameter is "year" or parameter is "keyword" or parameter is "author" or parameter is "year" or parameter is "language" or parameter is "type")`<br>
`      Write "Enter parameter value:"`<br>
`      Read value`<br>
`      If (parameter is "year")`<br>
`         Read end`<br>
Maybe I am missing something, but why does parameter "year" appear two times?<br>
`      Set results as empty list`<br>
`      If (parameter is "keyword")`<br>
`         Set count to 0`<br>
Intuitively, as we are adding string values to a list, I would not set any count, but I know that the book does it, so this is just a little sidenote. Maybe the count should be after the creation of the empty list, because otherwise it would implement only here.<br>
`         For record in dataset`<br>
`			      For keyword in record.keywords`<br>
`           	  If (keyword contains value)`<br>
`               	Add record to results`<br>
`      If (parameter is "author")`<br>
`         For record in dataset`<br>
`           For author in record.authors`<br>
`               If (record.authors contains value)`<br>
`               	Add record to results`<br>
`      If (parameter is "year")`<br>
`         For record in dataset`<br>
`           If (record.year is >= value and record.year is <= end)`<br>
`               Add record to results`<br>
I do not quite catch the logic behind the year parameter - could you explain it to me?<br>
`      If (parameter is "language")`<br>
`         For record in dataset`<br>
`           If (record.language is value)`<br>
`               Add record to results`<br>
`      If (parameter is "type")`<br>
`         For record in dataset`<br>
`         	  If (record.work-type is value)`<br>
`             	Add record to results`<br>
`      If (results size is 0)`<br>
`         Write "No results."`<br>
`   Else write "Error: invalid parameter."`<br>
`Else write "Error: empty dataset."`
