---
id: 4bebe554-70aa-47f7-ac01-5b505c2f0e2f
created: 1675139253410
updated: 1675142586176
---


## Important Links


## Sources

```dataview
TABLE
FROM  [[project.work.project-name]]
WHERE contains(file.name, "@.")
SORT file.day DESCENDING
```


## Meetings
```dataview
TABLE date
FROM  ""
WHERE contains(file.name, this.file.name + ".meeting" )
SORT file.day DESC
```



