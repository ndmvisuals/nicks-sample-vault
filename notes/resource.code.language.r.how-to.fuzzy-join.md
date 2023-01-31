---
id: dbp5dbb218d4voth8nlm6k5
title: Fuzzy Join
desc: ''
updated: 1674951254908
created: 1674578163295
---

```r
library(fuzzyjoin)
fuzzyjoin::stringdist_join(df1, df2,
                by = "name",
                mode = "left",
                method = "jw",
                max_dist = 99,
                distance_col = "dist") %>% 
  group_by(name.x) %>% 
  slice_min(order_by = dist, n=1) 
  
```


 o