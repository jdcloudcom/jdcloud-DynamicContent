# Product Overview
The TiDB Service is a distributed cloud database product created by JD Cloud in cooperation with PingCAP on the basis of the domestic open source NewSQL database TiDB, supporting both scenarios of OLTP and OLAP at the same time, realizing automatic horizontal scaling and distributed transactions with strong consistancy, which is simple in deployment, provided with an online asynchronous table based on a structure that the changes thereof will not affect the business while compatible with the MySQL protocol, so that the use and migration cost is reduced to an entremely low level.

## Supported Version
Beijing region currently supports TiDB 4.0 version.

## Main Features of TiDB Service 
1. TiDB Service can seamlessly extend the quantity of nodes as the growth of the data and can increase computational and storage ability approximately linearly;
2. Consistent distributed transaction; support standard ACID transaction; start transactions across multiple machines without affecting consistency;
3. Support most MySQL syntax; high compatibility for MySQL; the switch from MySQL to TiDB can be seamless with almost no need to modify the code; migration cost is extremely low;
4. Use multiple replica for data storage. When the master replica fails, there is no need for manual intervention and it can automatically guarantee the continuity of the sbusiness, which can realize the real sense of performing multiple tasks in different places.

## Common Operations
- [Create Instance](../Operation-Guide/Instance/Create-Instance.md)
- [Connect Instance](../Operation-Guide/Instance/Connect-Instance.md)
- [Create Account](../Operation-Guide/Account/Create-Account.md)
- [Create Backup](../Operation-Guide/Backup/Create-Backup.md)
  
## Billing
Now, TiDB is in the Beta stage and is free the users whose applications are approved.
