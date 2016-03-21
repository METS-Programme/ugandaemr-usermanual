 # Upgrading UgandaEMR 
## Upgrading a module
## Upgrading with a new WAR file 
1. Clean up the existing installation by: 
  * Delete the openmrs.war and openmrs folder in the directory C:\Program Files\UgandaEMR\apache-tomcat\webapps  
  * Delete all the modules in the directory C:\Application Data\OpenMRS\modules which is where any modules uploaded from the administration interface are stored. The modules in this directory override those added to the WAR file 
2. Copy the new WAR file to C:\Program Files\UgandaEMR\apache-tomcat\webapps  
3. Go to the UgandaEMR login link at http://localhost:8081/openmrs/ 
4. 
