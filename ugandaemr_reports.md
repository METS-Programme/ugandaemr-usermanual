## UgandaEMR Reports

### Reports Dashboard

The dashboard shows the avialable reports in the different categories:

1. Facility Reports - reports that support the running of a facility 
   * Appointments List
   * Missed Appointments List
   * ART Patient Export
   * Facility Death List
   * Exposed Infants Due for 1st PCR
   * Exposed Infants Due for 2nd PCR
   * Exposed Infants Due for Rapid Test
   * Exposed Infants Due for Appointment
   * OptionB+ Weekly SMS Report
   * Transfer Out List
   * Transfer In List
   * Lost Clients
   * Lost To Follow Up
   * Active Patients in Care
   * Due For Viral Load
   * Overdue for Viral Load
   * Stablity Assessment Report
2. Monthly Reports - HMIS reports that are run every month 
   * Case Based Surveillance EID Report
   * Adherence Report
   * Early Warning Indicator Report
   * HMIS 105 - 1: OPD
   * HMIS 105 Section 2.1 to 2.7: MCH
   * HMIS 105 Section 2.8 to 2.12: MCH - Child Services
   * HMIS 105 - 3 to 4: Outreach and HCT
   * HMIS 105 Section 5: SMC
   * HCA Annual Report
   * HCA 12 and 24 Months Report
3. Quarterly Reports - HMIS reports that are run every quarter
   * HMIS 106a Section 1A
   * HMIS 106a Section 1B
   * CBS Adult Quarterly Report
   * HMIS 177 Viral Load Addendum Quarterly Report
   * HMIS 106a With DSDM Aggregations
4. Registers - match the HMIS registers for different data collection forms 
   * HMIS 031: OPD Register
   * HMIS 035: SMC Register
   * HMIS 053: Patient Appointment Book
   * HMIS 055 : HCT Register
   * HMIS 071: ANC Register
   * HMIS 072: Maternity Register
   * HMIS 078: PNC Register
   * HMIS 080: Pre-ART Register
   * HMIS 081: ART Register
   * HMIS 082: EID Register
   * HMIS 096a: TB Register
5. MER Indicator Reports
   * TX Current 
   * TX New 
6. Early Warning Indicator Reports - run annually 
   * Lost To Follow Up
   * Pill Pickup
   * Viral Load Supression
7. Integration Data Exports 
   * Family Connect EMTCT Module Data Export - for data import into EMTCT module of Family Connect 

### Running a Report

#### HMIS 106A Section 1A

1. Login as a user with privileges to access the reports
2. Click the UgandaEMR reports link as in the image below
   ![UgandaEMR link](/assets/homepage_ugandaemr_reports_link.png)
3. On the Reports dashboard click the link to 106A Section 1A
   ![Reports Dashboard - 106A Section 1A link](/assets/reports_dashboard_106a_1a_link.png)
4. Enter the start date and end date for the quarter you wish to generate the report, then click the Run button
   ![106A 1A parameters](/assets/106A_1A_parameters.png)
5. This report will run for a while as shown by the progress icon 
   ![106A Section 1A processing](/assets/106A_1A_currently_processing.png)
6. Once the report is generated there are two options:
   * Download - downloads the generated report in Excel
   * Preserve - saves the data for the generated report, which will not change when data is updated or corrected later in the future 

![106A 1B Completed](/assets/106A_1A_download_preserve.png)

#### HMIS 106A Section 1B

1. Login as a user with privileges to access the reports
2. Click the UgandaEMR reports link as in the image below
   ![UgandaEMR link](/assets/homepage_ugandaemr_reports_link.png)
3. On the Reports dashboard click the link to 106A Section 1B
   ![Reports Dashboard - 106A Section 1B link](/assets/reports_dashboard_106a_1b_link.png)
4. Enter the start date and end date for the quarter you wish to generate the report, then click the Run button
   ![106A Section 1B Parameters](/assets/106A_1B_parameters.png)
5. This report will run for a while as shown by the progress icon
   ![106A 1B processing](/assets/106A_1B_currently_processing.png)
6. Once the report is generated there are two options:
   * Download - downloads the generated report in Excel
   * Preserve - saves the data for the generated report, which will not change when data is updated or corrected later in the future

![106A 1B Completed](/assets/106A_1B_download_preserve.png)

### Sending Reports to DHIS2

1. Set the DHIS2 UUID for the facility that is sending the data by:

   * Got to Legacy System Administration-&gt;Mantainance-&gt;Settings-&gt;Ugandaemr.
     > ![](assets/facilityUUID.PNG)

2. Set the DHIS2 Server URL, username and password by:

   * Got to Legacy System Administration-&gt;Mantainance-&gt;Settings-&gt;Ugandaemrsync

   * Save the Above settings

3. Download the Section 4 HTS Report in JSON Format

4. Click the SendToDHIS2 action item on the reports page

5. On the Preview window, confirm the values displayed and Click the SendToDHIS2 button

6. Wait for response message from the server. If the report is sent you will receive a message **"Report Has Been Successfully Sent"**

### Troubleshooting Tips

#### Unable to run reports due to an error loading Excel template or the report definition uuid cannot be found

![Error Loading Excel Resource - 1](/assets/error_loading_reporting_excel_resource.jpeg)  
![Error Loading Excel Resource - 2](/assets/error_loading_reporting_excel_resource-2.jpeg)

Reset all the reports by running the following script

```
/*!40101 SET @OLD_CHARACTER_SET_CLIENT = @@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS = @@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION = @@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE = @@TIME_ZONE */;
/*!40103 SET TIME_ZONE = '+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS = @@UNIQUE_CHECKS, UNIQUE_CHECKS = 0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS = @@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS = 0 */;
/*!40101 SET @OLD_SQL_MODE = @@SQL_MODE, SQL_MODE = 'NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES = @@SQL_NOTES, SQL_NOTES = 0 */;

DELETE FROM reporting_report_design_resource;
DELETE FROM reporting_report_design;
DELETE FROM global_property WHERE property LIKE 'reporting.reportManager%';
DELETE FROM serialized_object WHERE type LIKE 'org.openmrs.module.reporting.report%';

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;
```



