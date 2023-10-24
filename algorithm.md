`Set dataset to data/xml-dataset.xml`<br>
`If (dataset length is > 0)`<br>
`   Write "Enter search parameter:"`<br>
`   Read parameter`<br>
`   If (parameter is "keyword" or parameter is "author" or parameter is "year" or parameter is "language" or parameter is "type")`<br>
`      Write "Enter parameter value:"`<br>
`      Read value`<br>
`      If (parameter is "year")`<br>
`         Write "Enter end of year range:`"<br>
`         Read end`<br>
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
