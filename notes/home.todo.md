---
id: 1e0a0b06-6c99-4e18-b105-3db648d63d7b
created: 1675140873383
updated: 1675140873384
---

## Work
```dataview 
task 
FROM ""
WHERE contains(file.name, ".todo") AND contains(file.name, ".work") AND !completed
GROUP BY file.link 
SORT priority
```

## Freelance
```dataview 
task 
FROM ""
WHERE contains(file.name, ".todo") AND contains(file.name, ".freelance") AND !completed
GROUP BY file.link
```
## Personal
```dataview 
task 
FROM ""
WHERE contains(file.name, ".todo") AND !contains(file.name, ".npr") AND !contains(file.name, ".freelance") AND !completed
GROUP BY file.link
```
