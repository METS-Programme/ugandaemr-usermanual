# 3.2.0 - July 2021 

## New Features

1. [ART Regimen Lines](../program-workflows/art/regimen-lines.md) - this allows the capture of regimen substitutions and switches to aid the classification of patients according to the regimen lines they are on 
2. [TB Module ](../tuberculosis/introduction.md)
   * DS TB: HMIS TB 003 - TB Client Card Enrollment Page
   * DS TB: HMIS TB 003 - TB Client Card Followup Section
   * DR TB: HMIS TB 001 Second Line TB Treatment Card - Enrollment Page
   * DR TB: HMIS TB 001 Second Line TB Treatment Card - Followup Section
3. [COVID 19 Care and Treatment](../covid19/introduction.md) 
   * Case Investigation Form
   * Clinical Management
   * Discharge Form
   * Referral Form
   * Postmortem Form
4. Patient Line  Lists for MER Indicator reports - these help in verification of patient data used to generate the reports. These include TX_New, TX_Current 28 days and 90 days, TB ART, Tx TB, TX ML and TX RTT
5. Reports
   * HMIS 105 ANC Section
   * TPT Status Report
   * MER TX RTT
   * HMIS 106A 3.1 TB Section 
   * MER TX_TB Report
   * TB Register
   * Regimen Line Reports
6. New patient flag for clients bled for Viral load Testing
7. Ordering for Viral Load Results from CPHL in Retrospective Mode 
8. [UgandaEMR Mobile](../ugandaemr_mobile/README.md) for community drug dispensing and
## Bug Fixes 
1. Users can now export the correct DSDM models for a patient via Cohort builder 
2. Correcting of cohort used in MER TX_ML Reports 
3. Enable viral load history Display  on patient dashboard 
4. ART status display for all ART patients
5. Revision of the Lost to Follow-up Cohort To include the clients who turn Lost to Follow-up in the next reporting period

## Links to download files

### New Installation

For new machines with no UgandaEMR installed

* 32-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr3-2-0-installer-32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr3-2-0-installer-32bit.exe/download)
* 64-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr3-2-0-installer-64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr3-2-0-installer-64bit.exe/download)

### WAR File

[https://sourceforge.net/projects/ugandaemr/files/3.2.0/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/3.2.0/openmrs.war/download)

### Upgrade Installer

**For existing versions of UgandaEMR 2.0.x to 3.2.0**

* 32-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr\_upgrade\_from\_2.0.x\_to\_3.2.0\_32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr_upgrade_from_2.0.x_to_3.2.0_32bit.exe/download)
* 64-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr\_upgrade\_from\_2.0.x\_to\_3.2.0\_64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.2.0/ugandaemr_upgrade_from_2.0.x_to_3.2.0_64bit.exe/download)

**For existing versions of UgandaEMR 1.x to 3.2.0**

This upgrade path is no longer supported 

## Fixing Failed Installations and Upgrades

None