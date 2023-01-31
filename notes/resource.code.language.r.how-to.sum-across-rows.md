---
id: 9rjzc9cy43kvsiurlha8dfm
title: Sum across Rows
desc: ''
updated: 1674935935074
created: 1674580315054
---

## Sum across rows

```r
 mutate(total_deaths = rowSums(across(where(is.numeric))), .before = "x2015") 
```