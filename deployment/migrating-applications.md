---
title: Migrating your application between servers
---

## Step by step guide

1. Set up a [Failover Group](/docs/failover-groups/failover-groups)
2. Add the IP address of the Failover Group to your DNS record (allow 24 hours to propogate)
3. Set up a [managed backup](/docs/databases/database-backups) for your database 
4. [Clone your application](/docs/cloud-66-101/adding-updating-deleting#clone-an-application) to the new server
5. [Add databases](/docs/databases/adding-database) as required to the clone
6. Set up a [replication](/docs/databases/database-replication) between to the clone databases
7. Add the cloned application to the failover group as the secondary application
8. Put the primary site into [maintenance mode](/docs/deployment/using-maintenance-mode)
9. [Promote](/docs/toolbelt/toolbelt#databases-promote-replica) the cloned databases to masters
10. Switch the Failover Group to the new application
11. [OPTIONAL] Switch your DNS record to the new application

This method can be used to migrate applications between regions as well.

