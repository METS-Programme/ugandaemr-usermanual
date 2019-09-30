## HIV Recency Testing 
### Overview 
Recent HIV infection tests can provide real-time data about recent infections to identify
hot spots of current HIV transmission. 

In Uganda, this program is being rolled out with an initial 6 month pilot of 80 facilities from October 2019

### Installation and Configuration 
The recency program only requires an upgrade to UgandaEMR 3.0.0 which is available from the EMR portal at 

Once UgandaEMR has been upgraded, follow the steps below to complete the configuration changes. 

1. Login as a user with administrator privileges
![Login](images/log_in_as_admin_link.png)
2. Click legacy administration link as circled in the image below
![Legacy System Adminstration Link](images/legacy_system administration_link.png)
3. In the Maintenance section click Settings 
![](/assets/administrator_settings.jpg)
4. Click Ugandaemr and enter the DHIS2 uuid for the facility. This will be used as the username when submitting data to the central server
![DHIS2 setting](/assets/settings_ugandaemr.jpg) 
5. Click Ugandaemr sync to configure the settings for the recency server as below
 * Recency Server URL
 * Recency Server Password 
 * Hts Recency - set to true to enable the entry of Recency specific data on the HTS client card 
 ![Recency Settings](/assets/settings_ugandaemr_sync.png) 

### Data Capture Tools 
HIV Recency Testing is an extension of the national HIV Testing Algorithm, and is done for patients above 15 years whose HIV results are positive. 

The clients are requested to give consent for Recency testing and/or storage of their blood samples for future research.

This data is entered from the HTS ca


### Reporting

### Data Sharing with Central Server 

### Troubleshooting Tips 

  

