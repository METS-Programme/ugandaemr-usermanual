# 3.3.0 - December 2021 

## New Features

1. Community Pharmacy Dispensing (Lubwama add more details here)
   * ABC
   * Reports - TBD 
   * 
2. ART Regimen Lines 
   * Add a Regimen Change List Report to show the list of regimen change encounters in a period 
   * Added handling of transfer-in regimens along with the current regimen (captured on the ART Clinical Encounter page). This allows a regimen change to be recorded for a patient who has transferred in but has had an ART Clinical encounter recorded with a different regimen from the transfer-in regimen 
   * The Regimen Change form can be completed when a client only has the ART Summary page completed 
3. Reports 
   * Added HMIS 105 Section 2.2: Maternity report 
   * HMIS 106A uses the ART Regimen Lines feature to list patients on first line and second line regimens 
3. 

## Bug Fixes 
1. DSDM
   * Stability criteria now allows from 6 months to 1 year (Lubwama this is not clear to me from the Asana card)
   * 
2. Patient Flags
   * Transfer Out Flags (Baluku)
   * Missed Appointment for Community Encounters (Baluku)
3. ART Summary Card 
   * The list of transfer-regimens now includes all available DTG regimens 
4. HTS Client Card 
   * Added Social Network Strategy (SNS) as a reason for testing 
   * Added the ability to capture the ANC visit number when the ANC entry point is selected to enable accurate computation of the ANC1 and Post ANC1 segregations in the HTS_TST_Facility MER Indicator report 
5. Reports 
   * Active in Care report now exlcudes clients who transferred out, returned as transfer-ins and are active in care 
   * HTS_TST_Facility - added logic for computing the data across ANC1, ANC1+, Social Network Strategy and APN + Index Testing other than APN  
   * Appointment List, Lost and Lost to Followup Facility Reports now include client ART Clinic numbers 
   * TX_RTT report does not include the patients who had a clinical visit in the previous month 
   * 
6. 

## Links to download files

### New Installation

For new machines with no UgandaEMR installed

* 32-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr3-2-0-installer-32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr3-3-0-installer-32bit.exe/download)
* 64-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr3-2-0-installer-64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr3-3-0-installer-64bit.exe/download)

### WAR File

[https://sourceforge.net/projects/ugandaemr/files/3.3.0/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/openmrs.war/download)

### Upgrade Installer

**For existing versions of UgandaEMR 2.0.x to 3.3.0**

* 32-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr\_upgrade\_from\_2.0.x\_to\_3.3.0\_32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr_upgrade_from_2.0.x_to_3.3.0_32bit.exe/download)
* 64-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr\_upgrade\_from\_2.0.x\_to\_3.3.0\_64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr_upgrade_from_2.0.x_to_3.3.0_64bit.exe/download)

**For existing versions of UgandaEMR 1.x to 3.2.0**

This upgrade path is no longer supported 

## Fixing Failed Installations and Upgrades

None