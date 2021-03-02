## Setting Up The Shared Health Record Sync. 
There are four steps taken to setup the shared health record sync. 
    
    1. Setting up the URL where the data will be synced to
    
    2. Enable the Syncing of data. 
    
    3. Change local port, local username, and local password to match a user in ugandaemr. 
    
    4. Adding or changing the dhis2 uuid and the Facility Name.
    
###Setting up the URL 
In order to setup the URL, follow the steps below

    1. On the UgandaEMR Homepage Click on the System Administration Icon. This will navigate you to the System Administration page. 
    2. On the system administration page, click on the "UgandaEMR Sync" Icon. This will navigate you to the "UgandaEMR Sync" page. 
    3. On the "UgandaEMR Sync" Page, Click on the Sync Task Type Icon. This will navigate you to the Sync Task Type Page.
    4. On the "Sync Task Type" page, in the table below, find the "Sync Data to Shared Health Record" Item and click on the edit icon found the right under the "action" column. 
    This will navigate you to the edit page of the "Sync Data to Shared Health Record Sync Task Type". 
    5. On Edit Page for the "Sync Data to Shared Health Record Sync Task Type" change the url to "http://ugandaemr.mets.or.ug/shr/fhir/" and clink on the save button.
    
### Enable the Syncing of data.
In order to Enable The Syncing of data to the shared health record, follow the steps below

    1. On the UgandaEMR Homepage Click on the System Administration Icon. This will navigate you to the System Administration page. 
    2. On the system administration page, click on the "UgandaEMR Sync" Icon. This will navigate you to the "UgandaEMR Sync" page. 
    3. On the "UgandaEMR Sync" Page, Click on the Sync Settings icon. This will navigate you to the "Global properties for the Ugandaemrsync".
    4. On the "Global properties for the Ugandaemrsync" page, find the "Sync CBSFHIR Data" Item and change it's value to true. and Click on the "save" button. 
    

### Change local port, local username, and local password to match a user in ugandaemr. 

    1. On the UgandaEMR Homepage Click on the System Administration Icon. This will navigate you to the System Administration page. 
    2. On the system administration page, click on the "UgandaEMR Sync" Icon. This will navigate you to the "UgandaEMR Sync" page. 
    3. On the "UgandaEMR Sync" Page, Click on the Sync Settings icon. This will navigate you to the "Global properties for the Ugandaemrsync".
    4. On the "Global properties for the Ugandaemrsync" Check out the "CBS Local Host Port" if it matches the port on which the UgandaEMR Server is running.
    5. On the "Global properties for the Ugandaemrsync" Check out the "CBS Local Host Username" and "CBS Local Host Password" if they match any user who has administrative rights over they system.
    6. If there is any change you have made on  "CBS Local Host Port" or  "CBS Local Host Username" or "CBS Local Host Password". Click the "save" Buttom.
    

### Adding or changing the dhis2 uuid and the Facility Name.
The DHIS2 uuid is used to identify which facility is sending data. it needs to be set

    1. On the UgandaEMR Homepage Click on the Legacy System Administration Icon. This will navigate you to the Legacy System Administration page. 
    2. On the "System administration" page, Click on the "Health Center Configurations" icon.  This will navigate you to the "Global properties for the UgandaEMR".
    4. On the "Global properties for the UgandaEMR" Check out the "Dhis 2 Organizationuuid"  and "Health Center Name" if They are set appropriately. Change them where neccesory
    6. If there is any change you have made on  "Dhis 2 Organizationuuid"  and "Health Center Name". Click the "save" Buttom.

    

