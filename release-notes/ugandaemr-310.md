# 3.1.0 - October 2020 

## New Features

1. Clinical Workflows
   * Added TPT status to patient dashboard
   * Added ability to restrict return visit dates not to happen on public holidays and to limit the number of patients who have an appointment on a specific date 
   * TB Treatment Support using both Point of Care and Restrospective
   * Transfer in and out forms
   * Review of DSD Models.
      * Changed the duration of current regimen from 12 months to 6 months.
      * Clinicians determine whether the patient is stable or not.
      
      
   
2. Pharmacy and Dispensing
   * Ability to dispense drugs not the regimen combinations 
3. Added HMIS ACP 001 - Non-Supressed Viral Load Form and HMIS TB 003 Client Card 
4. Reports 
   * HMIS 106A Sections 1A and 1B 
   * Transitioned to DTG
   * Daily Missed Appointment Reports
   * TX\_ML Report
   

## Bug Fixes 
1. ART Summary Page and Clinical Assessment 
   * TPT and IP data was not being shown on edit of the forms 
   * Added a text field for other medications dispensed while essential medicines are limited to a drop down 
   * Added fields for Second and third alternative numbers on patient registration.
2. Point of Care  
   * TB Work Flow for both Drug Susceptible and Drug Resistant.
3. Patient Flags 
   * Non-supressed viral load message not displayed for patients with less than 1000 copies 
4. Reports 
   * Fixed errors in Maternity and ANC Registers 
   * Added current patient DSDM model and enrollment date to all facility reports which did not have those fields
   * 

## Links to download files

### New Installation

For new machines with no UgandaEMR installed

* 32-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr3-1-0-installer-32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr3-1-0-installer-32bit.exe/download)\)
* 64-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr3-1-0-installer-64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr3-1-0-installer-64bit.exe/download)\)

### WAR File

[https://sourceforge.net/projects/ugandaemr/files/3.1.0/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/3.1.0/openmrs.war/download)

### Upgrade Installer

**For existing versions of UgandaEMR 2.0.x to 3.1.0**

* 32-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr_upgrade_from_2.0.x_to_3.1.0_32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr_upgrade_from_2.0.x_to_3.0.4_32bit.exe/download)
* 64-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr_upgrade_from_2.0.x_to_3.1.0_64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.1.0/ugandaemr_upgrade_from_2.0.x_to_3.0.4_64bit.exe/download)

###NOTE 

* When upgrading to from 3.0.4 to 3.1.0 use the Upgrade option (Upgrade War File) found on the Start menu under All Programs/All Apps, UgandaEMR. If the option is not available, Download the update Scripts executable and run it to fix the upgrade option https://sourceforge.net/projects/ugandaemr/files/3.1.0/update-scripts-3.1.0.exe/download" 
