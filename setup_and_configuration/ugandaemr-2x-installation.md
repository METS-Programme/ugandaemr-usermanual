## UgandaEMR 2.x Installation Steps

1. Launch of the splash screen

![](/images/installer/splash.jpg)

1. License Agreement

![](/images/installer/1.2-agreement.jpg)

1. Selecting components to install. Select Restore Existing UgandaEMR database if you have any data backed up from any older version of UgandaEMR

![](/assets/Components.PNG)

1. Determining Installation directory

![](/images/installer/1.4-location.jpg)

1. ![](/assets/Components.PNG)

2. Confirm start menu item  
   ![](/images/installer/1.5-shortcut.jpg)

3. Install Java Runtime

![](/images/installer/2.1-inst-java.jpg)

![](/assets/Java1.1.PNG)

![](/assets/Java2.PNG)

![](/assets/Java3.PNG)

![](/assets/Java4.PNG)

![](/assets/Java5.PNG)

![](/assets/Java6.PNG)

7.Install MySQL  
![](/images/installer/3.1-mysql-configure.jpg)  
![](/images/installer/3.2-standard.jpg)  
![](/images/installer/3.3-comd1.jpg)  
![](/images/installer/3.4-password-for-root.jpg)  
![](/images/installer/3.5-execute.jpg)  
![](/images/installer/3.6-mysql-finished.jpg)

8.Install Tomcat  
This is a silent process in the background

9.Install Firefox  
![](/images/installer/5.3-fire-fox-inst.jpg)  
![](/images/installer/5.4-fire-standard.jpg)  
![](/images/installer/5.5-fire-fox-directory.jpg)  
![](/images/installer/5.1-fire.jpg)

10.Installing HeidiSQL  
![](/images/installer/1.1heidisql.PNG)

![](/images/installer/1.2heidisql.PNG)  
![](/images/installer/1.3heidisql.PNG)  
![](/images/installer/1.4heidisql.PNG)  
![](/images/installer/1.5heidisql.PNG)  
![](/images/installer/1.6heidisql.PNG)

![](/images/installer/1.7heidisql.PNG)

11.UgandaEMR Installation completed  
![](/images/installer/6.0-complete-installation.jpg)

### Troubleshooting Guide

#### OpenMRS Installation Wizard Appears

Incase the screen below appears, ![OpenMRS 2.0.5 Installation Wizard](/assets/intital_setup_screen.PNG)

To fix this:

1. Go to the start menu
2. Select UgandaEMR and select **Connect Database Path** and let it run and correct the path

![](/assets/PATH.png)  
3. Restart your computer  
4. Start UgandaEMR using the Desktop shortcut

#### Error occurs starting a large number due to metadamapping index creation issue

An error similar to the one below is shown in the log files:

```
WARN - ModuleFactory.startModuleInternal(788) |2018-03-22 16:58:39,213| Error while trying to start module: metadatamapping
org.openmrs.module.ModuleException: Unable to update data model using liquibase.xml. Module: Metadata Mapping
    at org.openmrs.module.ModuleFactory.runLiquibase(ModuleFactory.java:1034)
    at org.openmrs.module.ModuleFactory.startModuleInternal(ModuleFactory.java:728)
    at org.openmrs.api.context.Daemon$1.run(Daemon.java:74)
Caused by: liquibase.exception.MigrationFailedException: Migration failed for change set liquibase.xml::metadatamapping-2016-02-07-1310-b-mysql::kosmik:
     Reason: liquibase.exception.DatabaseException: Error executing SQL create index metadatamapping_idx_mdtm_mdclass on metadatamapping_metadata_term_mapping(metadata_class(255)): Duplicate key name 'metadatamapping_idx_mdtm_mdclass':
          Caused By: Error executing SQL create index metadatamapping_idx_mdtm_mdclass on metadatamapping_metadata_term_mapping(metadata_class(255)): Duplicate key name 'metadatamapping_idx_mdtm_mdclass':
          Caused By: Duplicate key name 'metadatamapping_idx_mdtm_mdclass'
```

**Fix:** Run the following SQL statement on the openmrs database then restart your computer

```
DROP index metadatamapping_idx_mdtm_mdclass ON metadatamapping_metadata_term_mapping;
```

#### MySQL Database Service keeps failing after an upgrade from UgandaEMR 1.x

![Upgrade database connection failure](/assets/upgrade_database_connection_failure.jpeg)

During the upgrade process, a configuration file is copied which may cause the system to crash due to a conflict in the sizes of the MySQL log files before upgrade and after upgrade. The steps below are to remove the log files causing the conflict

1. Open Services console and stop the UgandaEMR MySQL service 
2. Using windows explorer navigate to the MySQL folder, either _C:\Program Files\MySQL\Data_ or _C:\Program Files\MySQL 5.5\Data_
3. Delete the files named idblog 
4. Restart your computer 

The connection error should be resolved.

#### UgandaEMR Reports module does not start on upgrade to 2.0

There are two issues that have been identified that cause this:

* The maximum packet size for the MySQL server is too small so needs to be increased to 16M
* The serialized column where the Excel template is stored does not allow the special characters to be saved.

The fix is therefore a 2 step process:

1. Increase the maximum packet size for the MySQL server:

   * Open Notepad as an administrator - this is because the configuration file being edited in located in the C:\Program Files folder which has restrictions on who can edit the files. 
   * Open the file my.cnf \(or my in case Windows Explorer is configured to hide the extensions for files\)

     * Search for the variable max\_allowed\_packet and change is value to 16M
     * If the variable does not exists add it following the steps below:

     * Search for the section \[mysqld\]

     * Add max\_allowed\_packet=16M

   * Save the file

   * Restart your computer 
   * Run the following on the command prompt `mysql -u openmrs -p -e "SHOW GLOBAL VARIABLES LIKE 'max_allowed_packet'"` which will show 16777216 which means the variable has been changed 

2. Fix the character set of the serialized column by running the following SQL statement on the openmrs database:

       ALTER TABLE `serialized_object` MODIFY `serialized_data` MEDIUMTEXT CHARACTER SET utf8 NOT NULL;

3. Restart your computer

#### UgandaEMR Tomcat Service fails to start after re-installing UgandaEMR

This issue  has been identified to be  caused by the Improper un-installation process of UgandaEMR.

This is normally done by deleting of the the UgandaEMR Folder in the C:\Program Files folder which is not recommended.

The recommended un-installation process can be found [here](/uninstalling-ugandaemr/unistallinstalling-ugandaemr-older-versions.md).

To fix this issue. 

* Uninstall the UgandaEMR  you have just installed  in the recommended way 
* Open the command prompt as an Administrator by searching Command prompt in the windows task bar , and then press Ctrl+Shift+Enter
* On your command prompt, type "sc delete UgandaEMRTomcat " without quotes and press enter.
* If it shows no error, restart your computer and install UgandaEMR freshly as recommended [here.](/setup_and_configuration/ugandaemr-2x-installation.md)





