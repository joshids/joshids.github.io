---
layout: post
title: How to get LocalDB connection string
---
## How to get LocalDB connection string

If standard connection strings do not work for you e.g. (localdb)\{{instanceName}}, then you need to follow one of the following methods.

# Single Machine
* Open command prompt `cmd.exe`
* execute following command to get connection string for database:
<pre>
> sqllocaldb info
</pre>
![Image](/public/localDB_ConnectionString.png)
The arrow shows named pipe instance that we can use as connection string.
<p class="message">
Note that this will be different for each developer's machine. Which makes this ideal only for one machine Proof of Concept codes.
</p>

# CI Server / Team Environment

If you want to use Local DB for Unit Tests or other purposes, and also, need connection string to be same for each / all developers on the team, then you should use following steps:

1. Open SQL Server Object Explorer,
2. Refresh "SQL Server" node
3. Select your LocalDB instance e.g. `(localdb)\ProjectsV12`
4. Expand "Databases" node under `(localdb)\ProjectsV12`
5. Select the database you wish to connect to
6. Right Click and select `Properties`
7. From the Properties pane, select Vaue for `ConnectionString` property.
8. You can use this value as connection string in your projects.
9. That's all!
