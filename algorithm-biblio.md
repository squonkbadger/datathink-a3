`SET dataset TO OPEN("data/xml-dataset.xml")`<br>
`IF (dataset length > 0)`<br>
`   WRITE "Enter search parameter (options: k=keyword, a=author, y=year, l=language, t=type):"`<br>
`   READ parameter`<br>
`   IF (parameter is "k" OR parameter is "a" OR parameter is "y" OR  parameter is "l" OR parameter is "t")`<br>
`       WRITE "Enter parameter value (note: for year parameter, enter lower bound of year range):"`<br>
`       READ value`<br>
`       IF (parameter is "y")`<br>
`           WRITE "Enter the upper bound of year range:"`<br>
`           READ upper`<br>
`       SET results TO empty list`<br>
`       IF (parameter is "k")`<br>
`           FOR record IN dataset.xml.records`<br>
`               FOR keyword IN record.keywords`<br>
`           	    IF (keyword contains value)`<br>
`               	    ADD record TO results`<br>
`       IF (parameter is "a")`<br>
`           FOR record IN dataset.xml.records`<br>
`               FOR author IN record.contributors.authors`<br>
`                   IF (author contains value)`<br>
`               	    ADD record TO results`<br>
`       IF (parameter is "y")`<br>
`           FOR record IN dataset`<br>
`               IF (record.year is >= value AND record.year is <= upper)`<br>
`                   ADD record TO results`<br>
`       IF (parameter is "l")`<br>
`           FOR record IN dataset.xml.records`<br>
`               IF (record.language is value)`<br>
`                   ADD record to results`<br>
`       IF (parameter is "t")`<br>
`           FOR record IN dataset.xml.records`<br>
`         	    IF (record.work-type is value)`<br>
`             	    ADD record TO results`<br>
`       IF (results length is 0)`<br>
`           WRITE "No results."`<br>
`       ELSE FOR record IN results`<br>
`           FOR author IN record.contributors.authors`<br>
`                WRITE author+" "`<br>
`           WRITE "("+record.year+"). "+record.titles.title+". "`<br>
`           IF (record.work-type is "Book")`<br>
`               WRITE "("+record.edition+"). "+record.publisher+".<br>"`<br>
`           ELSE WRITE record.titles.secondary-title+", "`<br>
`           IF (record.work-type is "Conference paper" OR "Conference abstract")`<br>
`               WRITE record.volume+"("+record.number+"), "+record.pages+".<br>"`<br>
`           IF (record.work-type is "Article")`<br>
`               WRITE record.volume+"("+record.number+"), "+record.pages+". "+record.urls.related-urls.url+"<br>"`<br>
`           IF (record.work-type is "Preprint")`<br>
`               WRITE record.urls.related-urls.url+"<br>"`<br>
`   ELSE WRITE "Error: invalid parameter."`<br>
`ELSE WRITE "Error: empty dataset."`<br>
