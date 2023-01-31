---
id: s6y5jpkmgyrdzp8k8dibrqr
title: Mutate Across
desc: ''
updated: 1674935935073
created: 1674580497677
---

## Mutate across
```r

mutate(across(c(char_column1, char_column2), ~ as.numeric(.x)) %>%
mutate(across(everything(), as.character()))


```