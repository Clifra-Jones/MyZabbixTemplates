# Custom Zabbix Templates

Customized templates for Zabbix.

Here you will find custom built templates for Zabbix that we use in our organization.

Also included are some of the stock templates that we have modified to suit our needs.
If you find these useful please let me know.

## 7.0 Templates

### MSSQL by ODBC

There are several enhancements and fixes to this template that we have made over the stock template. We use this template extensively to monitor our SQL Server environment.

### Windows Process Monitoring by Zabbix Agent

This is a custom template we use in our environment. This template allows you to monitor individual processes for CPU, memory, and IO metrics.
By default this template only monitors process running under the SYSTEM and NT Authority/Network Service accounts.

When you apply this template it will discover all services running under these service account. This can be a potential problem if left with the defaults.

As in Quantum Physics, to monitor a phenomenon is to change it!

By monitoring too many processes you can overload the Zabbix agent and possibly your server if this is applied to to many hosts.

You should determine which processes you are most interested in and monitor ONLY those processes. We primarily monitor processes like the LSASS process on Domain controllers, The SQL Server service on SQL Servers, and our Anti-virus processes. 

To configure which processes to monitor change the macro {$PROC.NAMES.MATCHES} at the host level to include the process names you wish to monitor.

Example: ^(AuthLiteService|lsass|nxlog|SEDService|Sophos|SSPService|WmiPrvSE)

As stated earlier, care should be taken to not monitor too many processes.

### Windows by Zabbix Agent

This is a modified version of the Windows by ZAbbix Agent template we have modified for our use.
