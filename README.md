# python
```py
import csv
import re
file_name=input()
File = open("vacancies.csv", encoding='utf_8_sig',newline='\n')
reader = [row for row in csv.reader(File)]
naming=reader[0]
reader.pop(0)
for row in reader:
    if len(row)!=len(naming) or ('' in row):
        continue
    else:
        for i in range(len(naming)):
            row[i]=row[i].replace('\n',',')
            print(naming[i]+': ' + re.sub(r'\<[^>]*\>', '', row[i]))
        print()
```

