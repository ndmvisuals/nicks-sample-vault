---
id: akmyyqsd4m4w073xaf7orxh
title: Change Column Names
desc: ''
updated: 1674935935072
created: 1674580367870
---

## Changing column name of df with vector

```r
colnames(df) <- c(new_col1_name,new_col2_name,new_col3_name)


rename_with(~paste0("pct_",.),contains("diabetes_"))
```