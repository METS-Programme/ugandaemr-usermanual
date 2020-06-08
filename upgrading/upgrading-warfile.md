# Upgrading Warfile

## UgandaEMR 1.x

This will be done when there are multiple modules that need to be upgraded as a complete package, therefore a new WAR file is to be installed

1. Backup UgandaEMR
2. Stop Tomcat 
3. Clean up the existing installation by: 
   * Delete the following from the C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps folder:
     * openmrs.war 
     * openmrs folder   
   * Delete all the modules in the directory C:\Application Data\OpenMRS\modules which is where any modules uploaded from the administration interface are stored. The modules in this directory override those added to the WAR file 
   * Delete the C:\Application Data\OpenMRS\lucene folder as these indexes have to be rebuilt 
4. Copy the new WAR file to C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps
5. If needed run any upgrade SQL scripts  
6. Start Tomcat  
7. Go to the UgandaEMR login link at [http://localhost:8081/openmrs/](http://localhost:8081/openmrs/) 

## UgandaEMR 2.x

1. Goto  Start Menu  Select All Programs \(Windows 7\) or All apps \(Windows 10\).
2. Select UgandaEMR then select Upgrade UgandaEMR War File.
3. This will popup a window. in it select install.
4. Browse to the location of the war file. then upgrade and click open. 
5. When upgrade is complete it will give you a message to proceed to browser.

