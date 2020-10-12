# HIV Recency Testing

## Overview

Recent HIV infection tests can provide real-time data about recent infections to identify  
hot spots of current HIV transmission.

In Uganda, this program is being rolled out with an initial 6 month pilot of 80 facilities from October 2019

## Installation and Configuration

### Setting up UgandaEMR data sync

The recency program only requires an upgrade to UgandaEMR 3.0.0 which is available from the EMR portal at

Once UgandaEMR has been upgraded, follow the steps below to complete the configuration changes.

1. Login as a user with administrator privileges

   ![Login](../.gitbook/assets/log_in_as_admin_link.png)

2. Click legacy administration link as circled in the image below

   ![Legacy System Adminstration Link](../.gitbook/assets/legacy_system%20administration_link.png)

3. In the Maintenance section click Settings 

   ![Settings](../.gitbook/assets/administrator_settings%20%281%29.jpg)

4. Click Ugandaemr 

   Enter the DHIS2 uuid for the facility. This will be provided separately and will be used as the username when submitting data to the central server

   ![DHIS2 setting](../.gitbook/assets/settings_ugandaemr%20%281%29.jpg) 

5. Click Ugandaemr sync 

   Configure the settings for the recency server as stated below which are provided for your facility 

   * Recency Server URL - [https://ugisl.mets.or.ug:5000/recency](https://ugisl.mets.or.ug:5000/recency)
   * Recency Server Password \(provided separately\)
   * Hts Recency - set to true to enable the entry of Recency specific data on the HTS client card 

6. Restart UgandaEMR instance to enable the system to register the newly added variable in \(4\) and \(5\) above.

![Recency Settings](../.gitbook/assets/settings_ugandaemr_sync%20%281%29.png)

## Data Capture Tools

HIV Recency Testing is an extension of the national HIV Testing Algorithm, and is done for patients above 15 years whose HIV results are positive.

The clients are requested to give consent for Recency testing and/or storage of their blood samples for future research.

This data is entered following the steps in [HIV Testing Services Client Card](../data_entry/htc_card.md) which also includes the Recency Addendum

## Reporting

The reporting tools include the national HMIS tools are:  
1. HMIS ACP 019 HIV Testing Services Register  
2. HMIS 105 Health Unit Outpatient Monthly Report - Section 4  
3. MER Indicators - HTS\_RECENT, HCT\_TST\_Facility  
4. Data Exports

* HTS Client Card Export - CSV file containing all the fields entered on the HTS Card 
* Recency Data Export - CSV file with recency data fields 



## Data Sharing with Central Server

This is an automated process that occurs every hour until a successful submission is done in a day. Due to the small numbers involved, all the HTS records are sent each time, a process which will be improved as the program proceeds. The EMR gives the option to change the scheduled sync frequency.

#### Sync data flow

![](/assets/sync-data-flow.png)

A few key points to note:

* **Facility surveillance** data is collected in an EMR. Through an internet connection, the data will be sent to the Central Database at CPHL on regular intervals \(every day\).

* **UVRI data** is collected by the UVRI data management system. UVRI to send the data as excel files once a week to the Central database at CPHL. A web or file transfer interface will be used to upload the excel file with the previous week’s data.

* **CQI data** for all sites will be collected using ODK. This data will then be uploaded into the Power BI Analysis Database.

* **The central database** will hold all the data and combine/integrate the two datasets \(EMR and UVRI data\) into a single Recency dataset.

* **The Power BI Analysis Database** will disclose this data through dashboards to authorized users



#### Acquiring credentials

During or prior to recency activation at each site, METS/UCSF provide each facility with authentication details that can be added within the facility’s EMR. The credentials are created within MIRTH. MIRTH is the system that receives data from all facilities and verifies the credentials. It is installed at CPHL central server.

The username is preferred as the national DHIS2 ID. The password is a random set of characters and numbers.

#### Sync authentication

The supported authentication methods are stated in the API description below.

#### API description

The description of the API that receives the data can be found at this link.
https://github.com/METS-Programme/hie-documentation



#### Data dictionary

| **Data element name**                    | Datatype | NULL | **Value options**                                            | **Description**                                              |
| ---------------------------------------- | -------- | ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| dhis_orgunit_uuid                        | varchar  |      | text                                                         | DHIS2  organisation unit uuid                                |
| encounter_uuid                           | varchar  |      | text                                                         | Encounter  universal unique identifier                       |
| patient_id                               | varchar  |      | text                                                         | Patient  unique identifier within the instance of the EMR    |
| serial_number                            | varchar  | no   | text                                                         | HTS  number. This should be same number used in labeling HTS blood samples sent to UVRI |
| visit_date                               | datetime | yes  | datetime                                                     | Must be  YYYY-MM-DD format                                   |
| health_unit_name                         | varchar  | yes  | text                                                         | Name of  health facility                                     |
| health_unit_sub_county                   | varchar  | yes  | text                                                         | Name of  the subcounty of the client’s address. If not available, name of subcounty  the the health facility is located |
| health_unit_district                     | varchar  | yes  | text                                                         | Name of  the district of the client’s address. If not available, name of district the  health facility is located |
| sex                                      | varchar  | yes  | Female,  Male                                                | Gender  of client                                            |
| date_of_birth                            | datetime | yes  | datetime                                                     | Must be  YYYY-MM-DD format                                   |
| marital_status                           | varchar  | yes  | Never  married, Married/Cohabiting, Separated/Divorce, Widowed | Whether  client is married or not                            |
| accompanied_by                           | varchar  | yes  | Mother,  Father, Both Parents, 4.Other Specify               | If the  client is a child below 12 years                     |
| accompanied_by_other                     | varchar  | yes  | text                                                         | Only  filled if accompanied_by is other                      |
| hts_delivery_model                       | varchar  |      | Health  Facility(HF), Community                              |                                                              |
| hts_approach                             | varchar  |      | CICT/VCT,  PITC                                              |                                                              |
| health_unit_testing_entry_point          | varchar  |      | OPD,  Ward, ART clinic, TB clinic Nutrition unit, Young Child Clinic  (YCC), ANC, Maternity, PNC, SMC, Family Planning, STI clinic,  Other Specify |                                                              |
| health_unit_testing_entry_point_other    | varchar  | yes  | text                                                         |                                                              |
| community_testing_entry_point            | varchar  | yes  | Home  Based, Hotspot, Workplace, Outreach,  Drop in Centre (DIC),  Others Specify |                                                              |
| community_testing_entry_point_other      | varchar  | yes  | text                                                         |                                                              |
| reason_for_testing                       | varchar  |      | Assisted  PartnerNotification (APN), Index Client Testing other than APN,  PrEP4.PEP5.HIVSelf-TestPositive, Inconclusive HIV result,  Self-initiative, OthersSpecify |                                                              |
| reason_for_testing_other                 | varchar  | yes  | text                                                         |                                                              |
| special_category                         | varchar  |      | Prisoners,  PWIDs, Uniformed men, Migrant workers, Truckers, FisherFolks,  Refugees, Pregnant, Breastfeeding, AGYW, People with Disabilities  (PWD), Others (specify) |                                                              |
| special_category_other                   | varchar  | yes  | text                                                         |                                                              |
| first_time_hiv_test                      | varchar  | yes  | Yes,  No                                                     | Has  never tested before                                     |
| last_hiv_test_date                       | datetime | yes  | datetime                                                     | Must be  YYYY-MM-DD format                                   |
| last_hiv_test_result                     | varchar  | yes  | Positive,  Negative                                          | Test  results the last time tested                           |
| number_of_tests_last_12_months           | integer  | yes  | integer                                                      | Number  of times tested twelve months ago                    |
| number_of_sexual_partners_last_12_months | integer  | yes  | integer                                                      | Number  of sexual partners twelve months ago                 |
| prior_partner_testing                    | varchar  | yes  | Yes,  No, Don’t know, Not applicable                         | Spouse/partner  ever been tested for HIV before              |
| partner_recent_test_result               | varchar  | yes  | Positive,  Negative, Don’tknow                               | If  tested before the most recent test results for the spouse |
| pretest_counselling_done                 | varchar  | yes  | Yes,  No                                                     | Whether  client counseled before testing is done             |
| counseled_as                             | varchar  | yes  | Individual,  Couple, Group                                   | Whether  patient counseled alone or with other people present |
| hiv_final_test_result                    | varchar  | yes  | Positive,  Negative,  Inconclusive                           | final  Result of HIV test                                    |
| hiv_final_syphillis_duo_result           | varchar  | yes  | Non-Reactive  (NR), Reactive(R)                              |                                                              |
| recency_test_consent                     | varchar  | yes  |                                                              | Consented  For Recency Testing                               |
| recent_hiv_test_result                   | varchar  | yes  | Longterm,  Recent, Negative                                  | The  recency test result                                     |
| individual_result_received               | varchar  | yes  | Yes,  No                                                     | Received  results as individual                              |
| couple_result_received                   | varchar  | yes  | Yes,  No                                                     | Received  results as couples                                 |
| couple_result                            | varchar  | yes  | Discordant,  Concordant, negative, Concordant, positive      |                                                              |
| presumtive_tb                            | varchar  | yes  | Yes,  No                                                     | Client  has presumtive TB                                    |
| referred_to_tb_services                  | varchar  | yes  | Yes,  No                                                     | Presumtive  TB case referred for TB services                 |
| referred_to_hiv_care                     | varchar  | yes  | Yes,  No                                                     | Client  has been referred to HIV care or prevention services |
| referred_location                        | varchar  | yes  | text                                                         | Location  where client has been referred to for HIV Care     |
| counselor_name                           | varchar  | no   | text                                                         | EMR  username who made the data entry                        |
| uploaded_on                              | datetime | yes  | datetime                                                     | The  date and time the latest upload was received from the facility EMR |



## Troubleshooting Tips

### Unable to login to the central server

### Unable to send data to the central server

1. Restart the UgandaEMR instance at the facility. This is key after 
2. Observe the UgandaEMR alerts. Check if there are errors related to the following.
   * The UgandaEMR instance at the facility needs to have an internet connection for at least one hour within a day. 
   * 401 authentication error: This implies that either the recency server URL, username and or password are incorrect. Double check these values and also verify the credentials in Mirth.
3. Reduce the scheduled sync frequency to 10 minutes, restart UgandaEMR and observe the behaviour.

