---
title: Using production data in staging
---

There are three approaches to sharing data between environments, in order from safest to riskiest:

1.  Use the [database backup feature](/docs/databases/database-backups) to backup your production database and then [manually restore](/docs/databases/manage-backups#restoring-a-backup) it to the staging database. This is the safest alternative, as you're not working directly with your production database.

2.  [Set up a master/replica database on the production environment](/docs/databases/database-replication) and connect to the replica from the staging environment.

3.  [Share your production database with the staging application](/docs/databases/sharing-db), which would allow read/write access to the database from your staging enviroment. In this scenario, we **strongly urge** you to plan for how you will avoid writing test or junk data to your production database.

