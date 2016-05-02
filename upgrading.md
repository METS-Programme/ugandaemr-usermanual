# Upgrading UgandaEMR 
## Adding a new module
A new module is usually added to provide new functionality and features that were not currently available. 
1. Login as a user with administration privileges
2. Click legacy administration link as circled in the image below
![Legacy System Adminstration Link](images/legacy_system administration_link.png)
3. Select the Manage Modules link 
![Manage Modules](images/manage_modules_link.png)
4. On the Manage modules page, click the Add/Upgrade module button
![Add or Upgrade Module](images/add_or_upgrade_module_button.png)
5. In the popup window use the browse button under Upgrade Existing module to select the module file from your computer, then click Upload
![Add New Module](images/upload_new_module.png)
6. The module will be uploaded and started, which is seen by having a red button next to the name of the module 

## Upgrading a module
In this case the modules to be upgraded will be uploaded through the administration interface
1. Login as a user with administration privileges
2. Click legacy administration link as circled in the image below
![Legacy System Adminstration Link](images/legacy_system administration_link.png)
3. Select the Manage Modules link 
![Manage Modules](images/manage_modules_link.png)
4. On the Manage modules page, click the Add/Upgrade module button
![Add or Upgrade Module](images/add_or_upgrade_module_button.png)
5. In the popup window use the browse button under Upgrade Existing module to select the module file from your computer, then click Upload
![Upgrade Existing Module](images/upgrade_existing_module.png)
6. The module will be uploaded and started, which is seen by having a red button next to the name of the module 

## Upgrading with a WAR file 
This will be done when there are multiple modules that need to be upgraded as a complete package, therefore a new WAR file is to be installed
1. Clean up the existing installation by: 
  * Delete the openmrs.war and openmrs folder in the directory C:\Program Files\UgandaEMR\apache-tomcat\webapps  
  * Delete all the modules in the directory C:\Application Data\OpenMRS\modules which is where any modules uploaded from the administration interface are stored. The modules in this directory override those added to the WAR file 
2. Copy the new WAR file to C:\Program Files\UgandaEMR\apache-tomcat\webapps  
3. Go to the UgandaEMR login link at http://localhost:8081/openmrs/ 
## Common Troubleshooting Tips
### Error starting the module 
