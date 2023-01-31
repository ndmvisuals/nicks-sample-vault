---
id: rpwq66xqmf22ucpn5plbaoz
title: Read_multiple_files
desc: ''
updated: 1674935935073
created: 1674580226840
---

## Read in multiple files into one data frame
```r
files_to_df = function(path, type){
  # path is the string file path
  # type is in the format of "*csv"
  
  merged_data <- do.call(rbind, lapply(list.files(pattern = type, path = path), function(i){
  path = paste0(path, i)
  read_csv(path)}))
  
  return(merged_data)
}
```
