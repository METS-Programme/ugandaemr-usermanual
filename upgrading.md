# Upgrading UgandaEMR 
## Upgrading a module
In this case the modules to be upgraded will be uploaded through the administration interface
1. Login as a user with administration privileges
2. Click legacy administration link as circled in the image below
![Legacy System Adminstration Link](images/legacy_system administration_link.png)
3. Select the Manage Modules link 
![Manage Modules](manage_modules_link.png)
4. 

## Upgrading with a WAR file 
This will be done when there are multiple modules that need to be upgraded as a complete package, therefore a new WAR file is to be installed
1. Clean up the existing installation by: 
  * Delete the openmrs.war and openmrs folder in the directory C:\Program Files\UgandaEMR\apache-tomcat\webapps  
  * Delete all the modules in the directory C:\Application Data\OpenMRS\modules which is where any modules uploaded from the administration interface are stored. The modules in this directory override those added to the WAR file 
2. Copy the new WAR file to C:\Program Files\UgandaEMR\apache-tomcat\webapps  
3. Go to the UgandaEMR login link at http://localhost:8081/openmrs/ 
4. 
