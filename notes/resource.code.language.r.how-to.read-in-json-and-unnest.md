---
id: rqpu6ctz02an75ldgixoq98
title: Read in Json and Unnest
desc: ''
updated: 1674935935074
created: 1674580462235
---
## Read in json and unnest
```r

library(jsonlite)

newspaperdotcom <- fromJSON("../data/handmade/newspaperdotcom_data_complete.json")
# Flatten json file
ndc_flat <- flatten(newspaperdotcom)
# Convert flattened file to a dataframe
ndc_df <- as_tibble(ndc_flat)



 replace(is.na(.), 0)
```