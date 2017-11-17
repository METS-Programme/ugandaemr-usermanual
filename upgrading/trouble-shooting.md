### Common Troubleshooting Tips

#### backupdatabase script has an access denied error

![Backup database error](images/upgrade/upgrade_backup_database_error.png)  
This is because the password for root has changed from a blank password

1.Open the backup database \(or backupdatabase.bat\) file in Notepad and add the following to the line that starts with @mysqldump

`@mysqldump -ppassword`

password is the password of the root account, and there is no space after the -p

2.Doubleclick the backupdatabase file

#### upgradedatabase script has an error - openmrs\_backup database not found

This is because the installer did not create the openmrs\_backup database. Uninstall UgandaEMR and start again

![openmrs\_backup database not found](/images/upgrade/upgrade_error_openmrs_backup_not_found.png)

#### upgradedatabase script error 2003 - Can't connect to MySQL server on local host \(10061\)

![Access denied to openmrs\_backup](/images/upgrade/upgrade_access_denied_to_openmrs_backup.png)  
This is because the password for root has changed from a blank password

1.Open the upgradedatabase \(or upgradedatabase.bat\) file in Notepad and add the following to the line that starts with @mysqldump

`@mysql -ppassword`  
password is the password of the root account, and there is no space after the -p

2.Doubleclick the upgradedatabase file

#### Upgrade failed so need to reset environment

In case your upgrade fails, there is a need to restore the environment so that you can try again.

The steps are as follows:

1. Backup the openmrs database 
2. Delete the openmrs and openmrs\_backup databases
3. Create a new openmrs and openmrs\_backup databases
4. On the openmrs database run the following scripts:

   * new-install.sql - this one creates a blank database for UgandaEMR 
   * concept\_dictionary script - use the latest version  

5. Restart your computer so that UgandaEMR can start

6. Run the upgrade again

#### Error starting uploaded module

This is usually characterized by a green arrow next to the module name, an error message at the top of the Manage Modules page and a text box in the row of the module name with the words "Error starting! Click here for details"  
![Error starting module](/images/error_starting_module.png)  
1.Click the text box to find out the details of why the module did not start:

* If the error is caused by a missing module then upload the module following the steps above
* If the error is caused by a higher version of a module, then upgrade the module to that higher version. Please note that this may cause additional errors in other modules that may be incompatible with the higher version.
* If a lower version of a module is required, then you may need to upload a lower version of the module, though this may cause other modules to fail loading

2.Restart the computer which resets all UgandaEMR services.

#### UI Framework Error: Null Pointer Exception on Patient Registration

A common cause is blank entries in the address hierarchy during the upgrade process as seen in the link below  
![Null Pointer Exception on Patient Registration after Upgrade](/assets/upgrade_error_patient_reg_null_pointer.png)

1. Click the Administration link in the top menu as below:
   ![System Administration Link](/assets/upgrade_error_patient_reg_null_pointer_administration_link.png)
2. Click the Manage Address Hierarchy link on the administration dashboard
   ![Manage Address Hierarchy Link](/assets/manage_address_hierarchy_link.png)
3. Delete all the address hierarchy entries in the rectangle which are causing the error one level at a time 
   ![Cleanup Address Hierarchy Levels](/assets/cleanup_address_hierarchy_level.png)

#### Error starting Data Integrity Module

This error tends to happen from UgandaEMR 1.0.16 that requires this module to be available, which is based on upgrades from old versions of OpenMRS that had the data integrity module installed. The old version of a module left a dataintegrity tables installed, so the new version cannot replace some tables.

The fix involves deleting the dataintegrity\_rule table using different tools:

1. Command line

   * Connect to the database using the command 

   `mysql -u openmrs -p` which will request for a password

   * Change to the openmrs database 

   `use openmrs`

   * Delete the dataintegrity tables - not all of these may exist in your installation 

   `DROP TABLE IF EXISTS dataintegrity_run;`  
   `DROP TABLE IF EXISTS dataintegrity_result;`  
   `DROP TABLE IF EXISTS dataintegrity_column;`  
   `DROP TABLE IF EXISTS dataintegrity_check;`  
   `DROP TABLE IF EXISTS dataintegrity_integrity_checks;`  
   `DROP TABLE IF EXISTS dataintegrity_result;`  
   `DROP TABLE IF EXISTS dataintegrity_rule;`

   * Delete previous liquibase change logs for data integrity

   `DELETE FROM liquibasechangelog WHERE ID LIKE '%data-integrity%';`

   * Restart your computer 

2. Heidi SQL

   * Download the upgrade script from [https://sourceforge.net/projects/ugandaemr/files/1.0.16/dataintegritymodule\_cleanup-1.0.16.sql/download](https://sourceforge.net/projects/ugandaemr/files/1.0.16/dataintegritymodule_cleanup-1.0.16.sql/download)
   * Open a connection to the openmrs database on port 3306
   * Open File -&gt; Load SQL File and load the downloaded file 

**MYSQL Cant start After 2.0 Upgrade or installation**

Go to start menu, search for services.

Under Services look for mysql.

Stop mysql service

Go to C:\ProgramData\MySQL\MySQL Server 5.5\data

Delete ib\_logfile0,ib\_logfile1

Restart mysql from services.

**Tomcat Failing to start after installation or upgrade of 2.0**

Go to Menu search for Launch Tomcat Manager and clink on it

After check the notification area are click on tomcat icon 



