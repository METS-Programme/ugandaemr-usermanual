# UgandaEMR Reports

## Reports Dashboard

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
   * HTS\_RECENT Report
   * HCT\_TST\_Facility Report
   * Tx Current\_28Days Report
   * Tx Current\_90Days Report
   * Tx New Report
   * TB STAT Report
   * TB ART Report
   * PMTCT STAT Report
   * PMTCT ART Report
6. Early Warning Indicator Reports - run annually 
   * Lost To Follow Up
   * Pill Pickup
   * Viral Load Supression
7. Integration Data Exports 
   * Family Connect EMTCT Module Data Export - for data import into EMTCT module of Family Connect 

## Running a Report

1. Login as a user with privileges to access the reports
2. Click the UgandaEMR reports link as in the image below

   ![UgandaEMR link](../.gitbook/assets/homepage_ugandaemr_reports_link.png)

3. On the Reports dashboard click the link to 106A Section 1A

   ![Reports Dashboard - 106A Section 1A link](../.gitbook/assets/reports_dashboard_106a_1a_link.png)

4. Enter the start date and end date for the quarter you wish to generate the report, then click the Run button

   ![106A 1A parameters](../.gitbook/assets/106A_1A_parameters.png)

5. This report will run for a while as shown by the progress icon 

   ![106A Section 1A processing](../.gitbook/assets/106A_1A_currently_processing.png)

6. Once the report is generated there are two options:
   * Download - downloads the generated report in Excel
   * Preserve - saves the data for the generated report, which will not change when data is updated or corrected later in the future 

![106A 1B Completed](../.gitbook/assets/106A_1A_download_preserve.png)

## Report Definitions 
This section describes the cohorts used to build the different types of the reports to provide a basis for validating them 

### TX_NEW

Clients who started ART during the quarter at this facility 

| Includes                                     | Excludes                                  | Notes |
| -------------------------------------------- | ----------------------------------------- | ----- |
| Clients with an ART start date in the period |                                           |       |
|                                              | Patients transferred in during the period |       |

### TX_CURRENT - 90

This the MoH definition which defines active patients as those who have had a drug refill in the period, have a long refill past the period and patients who have not received ARVs within 89 days of their last missed drug pickup appointment. 

| Includes                                                     | Excludes                                                     | Notes                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Clients with Baseline ART Regimen                            |                                                              | Have started ART since they have a baseline regimen          |
| Clients who started ART in the period                        |                                                              | ART start date in the period                                 |
| Clients who transferred into care within the period          |                                                              |                                                              |
| Patients with an ART Encounter within the period and received drugs |                                                              |                                                              |
| Patients with Return visit date after the start date of the period |                                                              | 1. Patients scheduled to return in the period <br />2. Patients scheduled to return after the end of the period (long refills) |
|                                                              | Patients who died during by the end of the reporting period  |                                                              |
|                                                              | Patients transferred out in the reporting period             |                                                              |
|                                                              | Lost to Follow up - Patients who have spent 90 or more days without any clinical contact from their last scheduled appointment date in the reporting period |                                                              |

### TX_CURRENT - 28

This the PEPFAR definition which defines active patients as those who have had a drug refill in the period, have a long refill past the period and patients who have not received ARVs within 27 days of their last missed drug pickup appointment. 

| Includes                                                     | Excludes                                                     | Notes                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Clients with Baseline ART Regimen                            |                                                              | Have started ART since they have a baseline regimen          |
| Clients who started ART in the period                        |                                                              | ART start date in the period                                 |
| Clients who transferred into care within the period          |                                                              |                                                              |
| Patients with an ART Encounter within the period and received drugs |                                                              |                                                              |
| Patients with Return visit date after the start date of the period |                                                              | 1. Patients scheduled to return in the period <br />2. Patients scheduled to return after the end of the period (long refills) |
|                                                              | Patients who died during by the end of the reporting period  |                                                              |
|                                                              | Patients transferred out in the reporting period             |                                                              |
|                                                              | Lost to Follow up - Patients who have spent 28 or more days without any clinical contact from their last scheduled appointment date in the reporting period |                                                              |