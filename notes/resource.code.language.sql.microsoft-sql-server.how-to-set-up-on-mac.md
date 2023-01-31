---
id: fgvn0qsm86lny26rjo2mn5i
title: How to Set up on Mac
desc: ''
updated: 1674935902667
created: 1674935902667
---

- https://www.youtube.com/watch?v=glxE7w4D8v8


```
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=yourStrong(!)Password" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2022-latest
```


docker run -e "ACCEPT_EULA=1" -e "MSSQL_SA_PASSWORD=reallyStrongPwd123" -e "MSSQL_PID=Developer" -e "MSSQL_USER=SA" -p 1433:1433 -d --name=sql mcr.microsoft.com/azure-sql-edge


```
`docker run -d --name MySQLServer -e` `'ACCEPT_EULA=Y'` `-e` `'SA_PASSWORD=your_password'` `-p 1433:1433 mcr.microsoft.com``/azure-sql-edge`
```

```
docker run -e "ACCEPT_EULA=1" -e "MSSQL_SA_PASSWORD=reallyStrongPwd123" -e "MSSQL_PID=Developer" -e "MSSQL_USER=SA" -p 1433:1433 -d --name=sql mcr.microsoft.com/azure-sql-edge
```


https://www.quackit.com/sql_server/mac/how_to_restore_a_bak_file_using_azure_data_studio.cfm

https://www.youtube.com/watch?v=Lmzq0S9K3Ag

https://www.youtube.com/watch?v=h0nxCDiD-zg
## How to restore .bak file
- 