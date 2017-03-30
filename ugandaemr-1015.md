## UgandaEMR 1.0.15 Release Notes
### Bug Fixes
1. Registration page 
  * Correction of marital status values to match those on the ART card
2. 

### New Features
1. Data Validation rules - see Data Quality link on the home page with the following rules:
  * Patients on ART without ART start date 
  * Patients with ART summary page and no encounters 
  * Patients on ART without an ART start regimen 
  * Patients on ART with other regimen - this was common where the regimens were not added, so now the need is to move all patients with other to the respective regimen to improve computation of patients on first and second line 
  * Exposed Infants with Summary page and no encounters 
  * Exposed Infants with Encounters and no Summary page 
  * Patients on ART with summary page and no encounters 
  * Patients on ART with encounters but no summary page
  * Patients with more than one ART summary page 
  * Patients with more than one encounter of the same type on the same date 

2. Support for viral load results on the ART Encounter page with the status values:
  * Detected allows the entry of results with a minimum of 20 copies per ml to be added 
  * Undetected saves a value of 1
  * Sample Rejected saves no value, therefore the last value remains valid 

3. Registration page: 
  * Add a field to capture Occupation 
  * Add up to 3 phone numbers 
   
4. Data Entry forms
  * Enable the SMC card to be entered only once per patient 
  * ART Encounter there are additional vitals for BP, temperature that can be captured 
4. List of encounters shows the person who entered the encounter 
5. Ability to view an encounter and print the form similar to the old OpenMRS 1.6.3
6. Search patient
  * Two more fields martial status and location
  * Now has a button to register patient at the bottom of the page to ease this flow 
7. Reports:
  * Add ART Patient Export that exports all patients on ART with important data items - need feedback on what may be missing data wise 
  * Fixes to 106A based on current feedback from testers - more tests being carried out on data submitted during the October to December 2016 from sites that are providing feedback 
8. Automated backup runs at 4:00pm everyday 
9. Ability to mark patient as dead

### Links to download files
### Recommended Upgrade Paths depending on existing UgandaEMR version 
1. 1.0.14 - Replace the WAR file with a new one 
2. 1.0.13-SNAPSHOT - Replace the WAR file with a new one 
2. 1.0.12 and lower versions 
  - Run the concept script 
  - Deploy the WAR file 






  