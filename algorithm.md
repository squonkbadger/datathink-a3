`Set dataset to data/xml-dataset.xml`<br>
`If (dataset length is > 0)`<br>
`   Write "Enter search parameter:"`<br>
`   Read parameter`<br>
`   If (parameter is "year" or parameter is "keyword" or parameter is "author" or parameter is "year" or parameter is "language" or parameter is "type")`<br>
`      Write "Enter parameter value:"`<br>
`      Read value`<br>
`      If (parameter is "year")`<br>
`         Write "Enter end of year range:`<br>
`         Read end`<br>

Maybe I am missing something, but why does parameter "year" appear two times?<br>

The idea was that the parameter "year" would allow the user to specify a range rather than a specific year. This is done so that if the parameter entered by the user is "year", the algorithm asks for a second value to be the end of the range, which is checked later with If (record.year is >= value and record.year is <= end). I have now added a Write line to prompt the user, hopefully it is more clear, but if it's too messy or we prefer to just use a specific year we can do that too of course! - Badger<br>

`      Set results as empty list`<br>
`      If (parameter is "keyword")`<br>

Intuitively, as we are adding string values to a list, I would not set any count, but I know that the book does it, so this is just a little sidenote. Maybe the count should be after the creation of the empty list, because otherwise it would implement only here.<br>

The count was from when I tried to do the iteration using while, I forgot to remove it, sorry! - Badger<br>

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
I wrote about it in the comment earlier in the algorithm, but we can change it to only use value rather than value/end as lower and upper bound - Badger<br>
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
