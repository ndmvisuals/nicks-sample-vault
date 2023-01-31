---
id: pkq7wpeks17gqd20jlctssr
title: Make Directory
desc: ''
updated: 1674935935064
created: 1674589493472
---

```bash

#!/bin/bash


mkdir -p {analysis,data/{documentation,handmade,html_reports,processed,public,source},etl,publish,viz,webscrapers}

  

find . -type d -exec touch {}/readme.md \;

```