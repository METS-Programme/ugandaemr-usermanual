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

```DROP index metadatamapping_idx_mdtm_mdclass ON metadatamapping_metadata_term_mapping;
```



          
          

