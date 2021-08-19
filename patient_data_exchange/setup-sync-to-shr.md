## Setting Up The Sync of Data to Central Server. 
There are four steps taken to setup the syncing data to central server. 
    
    1. Setting up the URL where the data will be synced to
    
    2. Enable the Syncing of data. 
    
    3. Adding or changing the dhis2 uuid and the Facility Name.
    
### Setting up the URL 
In order to setup the URL, follow the steps below

    1. On the UgandaEMR Homepage Click on the System Administration Icon. This will navigate you to the System Administration page. 
    2. On the system administration page, click on the "UgandaEMR Sync" Icon. This will navigate you to the "UgandaEMR Sync" page. 
    3. On the "UgandaEMR Sync" Page, Click on the Sync Task Type Icon. This will navigate you to the Sync Task Type Page.
    4. On the "Sync Task Type" page, in the table below, find the "Sync Data to Shared Health Record" Item and click on the edit icon found the right under the "action" column. 
    This will navigate you to the edit page of the "Sync Data to Shared Health Record Sync Task Type". 
    5. On Edit Page for the "Sync Data to Shared Health Record Sync Task Type" change the url to "http://ugandaemr.mets.or.ug/shr/fhir/" and clink on the save button.
    
### Enable the Syncing of data.
In order to Enable The Syncing of data to the central server, follow the steps below

    1. On the UgandaEMR Homepage Click on the System Administration Icon. This will navigate you to the System Administration page. 
    2. On the system administration page, click on the "UgandaEMR Sync" Icon. This will navigate you to the "UgandaEMR Sync" page. 
    3. On the "UgandaEMR Sync" Page, Click on the Sync Settings icon. This will navigate you to the "Global properties for the Ugandaemrsync".
    4. On the "Global properties for the Ugandaemrsync" page, find the "Sync CBSFHIR Data" Item and change it's value to true. and Click on the "save" button. 

### Adding or changing the dhis2 uuid and the Facility Name.
The DHIS2 uuid is used to identify which facility is sending data. it needs to be set

    1. On the UgandaEMR Homepage Click on the Legacy System Administration Icon. This will navigate you to the Legacy System Administration page. 
    2. On the "System administration" page, Click on the "Health Center Configurations" icon.  This will navigate you to the "Global properties for the UgandaEMR".
    4. On the "Global properties for the UgandaEMR" Check out the "Dhis 2 Organizationuuid"  and "Health Center Name" if They are set appropriately. Change them where neccesory
    6. If there is any change you have made on  "Dhis 2 Organizationuuid"  and "Health Center Name". Click the "save" Buttom.