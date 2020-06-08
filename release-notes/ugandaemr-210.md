# 2.1.0

## New Features

1. Patient Flags - these allow highlighting information on the patient dashboard following the traffic light coloring, green \(good\), orange \(take note\), red \(take action\). The summary of flags by color codes are:
   * Green 
     * Upcoming Appointment
     * Due for First Viral Load
     * Due for Routine Viral Load
     * Due for 1st DNA PCR
     * Due for 2nd DNA PCR
     * Due for Rapid Test
   * Orange 
     * Missed Appointment
   * Red 
     * Overdue for First Viral Load
     * Overdue for Routine Viral Load
     * Lost, Lost to Followup
     * Overdue for 1st DNA PCR
     * Overdue for 2nd DNA PCR
     * Overdue for Rapid Test
     * Has Detectable Viral Load
2. Ability to disable some of the patient flags to improve performance 
3. Differentiated Service Model
   * All patients enrolled in HIV care are placed in the FBIM model 
   * During the data capture for an ART Encounter the model can be changed 
   * Only stable patients can be moved to community models 
   * The history of the patient's models is displayed on the patient's dashboard 
4. Patient Dashboard - added the following sections 
   * Summary from Last Visit - selected data elements from the last ART encounter 
   * Viral Load History - shows a history of viral load results  
   * Directions to address 
5. Data Tools Update 
   * DTG regimens have been added to the ART Summary and Encounter pages  
   * ART Encounter Page - duration on ART and duration on current regimen are automatically computed
6. New Data tools
   * Intensive Adherence Counselling \(IAC\) form 
7. Reports
   * All reports can be exported as CSV
   * New Facility Reports 
     * Due for Viral Load
     * Overdue for Viral Load
     * Transfer In
     * Transfer Out
     * Lost Clients
     * Lost to Followup
     * Active Clients in Care which also includes support for long refills where a patient does not come into a facility for more than 3 months 
     * Non-Suppressed Viral Load
     * Patient Stability Assessment Report
     * Patient DSDM Model Report 
     * HTC Card Data Export 
   * New MER Indicator Reports 
     * TX\_CURR \(for 30 days and 90 days\)
     * TX\_NEW
     * TB STAT
     * TB ART
     * TX\_TB
     * PMTCT STAT 
   * Early Warning Indicators reports 
     * Lost to Follow-up
     * Pill Pickup
     * Viral Load Suppression 
   * Integration Data Exports
     * Family Connect EMTCT Module
   * Registers 
     * HIV Exposed Infants Register
8. Updated address hierarchy on the patient registration page to match the current version in DHIS2 as of April 2019
9. Improved performance by:
   * Removed chart search, Atlas modules 
   * Data Entry Statistics and FHIR modules are not started by default  

## Bug Fixes

1. Data quality violations were not removed when fixes are applied  
2. ART Summary page would not save with date validations for Transfer In
3. Added addresses to all patient level reports 
4. Corrected reports which had errors during running  

## Links to download files

This release is a drop in WAR file upgrade for UgandaEMR 2.0.0, however upgrades from 1.x require the use of the upgrade installer due to changes in the Java version required from Java 7 to Java 8

### WAR File

[https://sourceforge.net/projects/ugandaemr/files/2.1.0/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/openmrs.war/download)

### Upgrade Installer

**For existing versions of UgandaEMR 2.0.0 to 2.1.0**

1. 32 bit upgrade installer [https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr\_upgrade\_from\_2.0.0\_to\_2.1.0\_32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr_upgrade_from_2.0.0_to_2.1.0_32bit.exe/download)
2. 64 bit upgrade installer [https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr\_upgrade\_from\_2.0.0\_to\_2.1.0\_64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr_upgrade_from_2.0.0_to_2.1.0_64bit.exe/download)

**For existing versions of UgandaEMR 1.x**

1. 32 bit upgrade installer [https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr\_upgrade\_from\_1.x\_to\_2.1.0\_32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr_upgrade_from_1.x_to_2.1.0_32bit.exe/download)
2. 64 bit upgrade installer [https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr\_upgrade\_from\_2.0.0\_to\_2.1.0\_64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr_upgrade_from_2.0.0_to_2.1.0_64bit.exe/download)

### New Installation

1. 32 bit installer [https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr2-1-0-installer-32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr2-1-0-installer-32bit.exe/download)
2. 64 bit installer [https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr2-1-0-installer-64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr2-1-0-installer-64bit.exe/download)

## Fixing Failed Installations and Upgrades

**Fix to Patient flags in case its Not started**

Download The script drop\_patient flags [https://sourceforge.net/projects/ugandaemr/files/2.1.0/scripts/drop\_patientflags.sql/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/scripts/drop_patientflags.sql/download) and run it using the Execute Mysql option you will find on the start menu of windows under programs or apps under UgandaEMR

**Fix to Reports failing to start or run.**

Download The script reoprts [https://sourceforge.net/projects/ugandaemr/files/2.1.0/scripts/reports.sql/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/scripts/reports.sql/download) and run it using the Execute Mysql option you will find on the start menu of windows under programs or apps under UgandaEMR

**Fixing 404 after upgrade from 2.0.0 to 2.1.0**

This happens in case tomcat is not yet stopped and a war file is over written. It can be fixed by rerun the upgrade of \(from 2.0.0 to 2.1.0\).

**Fixing 404 after upgrade from 1.x to 2.1.0**

This happens in case tomcat is not yet stopped and a war file is over written. It can be fixed by using the upgrade with war file that is found on the start menu of windows under programs or apps under UgandaEMR.

NB You will need a war file which you can download from either the emrportal under downloads or use this link [https://sourceforge.net/projects/ugandaemr/files/2.1.0/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/openmrs.war/download)

## Noteable contributions

We would like to recognize the noteable contribution of the following partners, and facilities in this release

1. Baylor and Rwenzori Region health facilties - feedback on facility level reports and field testing of DSDM modules 
2. MUJHU through Mulago and Kawempe Hospital facilities - ANC and Maternity data collection and reporting tools, especially the need to export reports as CSV format for further analysis 
3. Alive Medical Services and ISS Clinic Mulago - stress testing and continuous improvements to the patient clinician facing dashboard page 

