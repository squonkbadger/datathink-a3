> As I have some knowledge in programming, it is somewhat easier for me to think in code, and not pseudocode – thus, I will write the pseudocode in algorithm markdown file, and keep this file as a commented draft with examples in python. I hope that it is not too confusing!

## Pseudocode

Importing necessary libraries to the program.
`Import necessary libraries`

Loading the dataset.
`Load dataset into program accessing dataset's path`

Printing the dataset.
`Print the dataset to see whether the data was imported correctly`

> Here a lot of depends on which kind of data we are dealing with – even though we are not writing actual code, this decision still influences our other choices. In the Python code example, the file is in TXT file format, but I would personally like to process tabular data in CSV or TSV file formats. EndNote also allows exporting XML file format. I will write the pseudocode as if we have tabular data (but we can, of course, change it later).

Our goal is to check every row in the column named keyword and return the title of the article if it is written about the selected keyword. The keyword is determined by the user.

Define first variable.
`Define variable result as empty list`
 
Define second variable.
`Define variable keyword as user input`

Iteration and selection.
```
FOR row in dataset:
    IF keyword = keyword in keywords column
        Add article title in result
    ELSE 
        Continue
```

Printing the titles, which had the keyword that the user looked for.
`Print result`

## Python code
NB! I have used for experimenting my own tabular TSV dataset, so some parameters are different.

```
import pandas as pd
df = pd.read_table('erb_multimedia.tsv')
print(df)

result = []

keyword = input('Please enter a keyword: ')

for index, row in df.iterrows():
    if keyword==row["language"]:
        result.append(row["ISBN"])
    else:
        continue

print(result)
```