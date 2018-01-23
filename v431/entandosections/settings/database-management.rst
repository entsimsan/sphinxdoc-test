.. _database-management:

.. index::
   single: Database Management

***************************************************
Database Management
***************************************************

.. index::
   single: Database Backup

.. _database-backup:

Backup Entando Database
-------------------------

Access Settings >> Database

Click on the button Create a backup, the system will show you in details what is going to be dumped, please read the list very carefully before assuming what you will find backed up in the process.
The database backup is accessible via Settings >> File Browser >> protected >> databaseBackups.
Every single table of the Entando system is dumped in a sql script format.
Resides in /project-name/src/main/webapp/protected in the filesystem of the server on which Entando is installed.
