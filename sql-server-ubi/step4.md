# Connect to SQL Server running in the container

Launch an interactive bash shell in the container connecting to database instance 0 (*mssqlDB0*)

`podman exec -it mssqlDB0 "/bin/bash"`{{execute T3}}

Connect with *sqlcmd* and run a T-SQL statement to get the servername and the version of SQL Server running on the server

> **NOTE:** sqlcmd is not in the path by default, so you have to specify the full path

`/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P 'RedHat1!' -Q "select @@servername, @@version"`{{execute T3}}
 
<pre class="file">
-------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
mssqlcontainer0                   Microsoft SQL Server 2019 (RTM-CU5) (KB4552255) - 15.0.4043.16 (X64)
        Jun 10 2020 18:25:25
        Copyright (C) 2019 Microsoft Corporation
        Developer Edition (64-bit) on Linux (Red Hat Enterprise Linux 8.2 (Ootpa)) <X64>

(1 rows affected)
</pre>

Verify that the hostname of the running container is *mssqlcontainer0*, and the version of SQL Server running is 2019.
