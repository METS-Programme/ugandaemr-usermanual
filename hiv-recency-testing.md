## HIV Recency Testing

### Overview

Recent HIV infection tests can provide real-time data about recent infections to identify  
hot spots of current HIV transmission.

In Uganda, this program is being rolled out with an initial 6 month pilot of 80 facilities from October 2019

### Installation and Configuration

#### Setting up server authentication

HTS records are sent by UgandaEMR to a secure server at CPHL. Authentication details have to be created within the CPHL MIRTH server for each site that is configured to send data \(config process explained below\).

1. Download and install the Mirth Connect Administrator Launcher tool.
2. Using the MIRTH admin tool, connect to https://ughim.cphluganda.org/recency![](/assets/Screenshot 2019-10-14 at 11.11.38.png)
3. Under channels menu \(from left side of the admin panel\), right click and select _Edit Channel_ named **http-listener-file-writer**. You will be given the edit windows shown below. Select the _Source_ tab and click the **New** button under HTTP Authentication. Provide the DHIS2 UUID as the username and a password. We recommend six character password that is alphanumeric.
   ![](/assets/Screenshot 2019-10-14 at 11.24.19.png)

4. To save the credentials added, you will have to attempt to navigate away from the edit window. The interface will request to save changes. Click Yes.

5. Go back to the channels, right click on the **http-listener-file-writer** and select _Deploy Channel_.

#### Setting up UgandaEMR data sync

The recency program only requires an upgrade to UgandaEMR 3.0.0 which is available from the EMR portal at

Once UgandaEMR has been upgraded, follow the steps below to complete the configuration changes.

1. Login as a user with administrator privileges
   ![Login](images/log_in_as_admin_link.png)
2. Click legacy administration link as circled in the image below
   ![Legacy System Adminstration Link](images/legacy_system administration_link.png)
3. In the Maintenance section click Settings 
   ![Settings](/assets/administrator_settings.jpg)
4. Click Ugandaemr and enter the DHIS2 uuid for the facility. This will be used as the username when submitting data to the central server
   ![DHIS2 setting](/assets/settings_ugandaemr.jpg) 
5. Click Ugandaemr sync to configure the settings for the recency server as below which are provided for your facility 
   * Recency Server URL
   * Recency Server Password 
   * Hts Recency - set to true to enable the entry of Recency specific data on the HTS client card 
6. Restart UgandaEMR instance to enable the system to register the newly added variable in \(4\) and \(5\) above.

![Recency Settings](/assets/settings_ugandaemr_sync.png)

### Data Capture Tools

HIV Recency Testing is an extension of the national HIV Testing Algorithm, and is done for patients above 15 years whose HIV results are positive.

The clients are requested to give consent for Recency testing and/or storage of their blood samples for future research.

This data is entered following the steps in [HIV Testing Services Client Card](/htc_card.md) which also includes the Recency Addendum

### Reporting

The reporting tools include the national HMIS tools are:  
1. HMIS ACP 019 HIV Testing Services Register   
2. HMIS 105 Health Unit Outpatient Monthly Report - Section 4  
3. MER Indicators - HTS\_RECENT, HCT\_TST\_Facility  
4. Data Exports

* HTS Client Card Export - CSV file containing all the fields entered on the HTS Card 
* Recency Data Export - CSV file with recency data fields 

### Data Sharing with Central Server

This is an automated process that occurs every hour until a successful submission is done in a day. Due to the small numbers involved, all the HTS records are sent each time, a process which will be improved as the program proceeds

### Troubleshooting Tips

#### Unable to login to the central server

#### Unable to send data to the central server

1. Restart the UgandaEMR instance at the facility. This is key after 
2. Observe the UgandaEMR alerts. Check if there are errors related to the following.
   1. The UgandaEMR instance at the facility needs to have an internet connection for at least one hour within a day. 
   2. 401 authentication error: This implies that either the recency server URL, username and or password are incorrect. Double check these values and also verify the credentials in Mirth.
3. Reduce the scheduled sync frequency to 10 minutes, restart UgandaEMR and observe the behaviour.



