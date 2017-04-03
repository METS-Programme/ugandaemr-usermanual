## UgandaEMR 1.0.15 Release Notes
### Bug Fixes
1. Registration page 
  * Correction of marital status values to match those on the ART card
2. ART Card Summary Page
  * Corrected validation errors on lost to followup and Transfer out section of outcomes 
  * 
3. ART Encounter page 
  * BP, temperature can be captured
4. SMC Card 
  * Can only be entered once per patient 
  * Added missing serial number 
  * Added Assistant Circumciser who is included on the card 
  * 

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
  * Add a field to capture Occupation that can be leveraged for key populations 
  * Add up to 3 phone numbers  
4. Encounters:
  * List of encounters shows the person who entered the encounter and the date when they entered it similar to OpenMRS 1.6.x versions  
  * Ability to view an encounter and print the form similar to the old OpenMRS 1.6.3
6. Search patient
  * Two more fields martial status and location added to list
  * A button to register patient at the bottom of the page to simplify the flow 
7. Reports:
  * Add ART Patient Export that exports all patients on ART with important data items - need feedback on what may be missing data wise 
  * Fixes to 106A based on current feedback from testers - more tests being carried out on data submitted during the October to December 2016 from sites that are providing feedback 
8. Automated backup scheduled run at 4:00pm everyday 
9. Ability to mark patient as dead
10. No need to run SQL scripts to add concepts when upgrading from 1.0.14 and higher versions 

### Links to download files
1. AIJAR module - https://sourceforge.net/projects/ugandaemr/files/1.0.15/aijar-1.0.15.omod/download
2. WAR file - https://sourceforge.net/projects/ugandaemr/files/1.0.15/openmrs.war/download
3. 32 bit installer - https://sourceforge.net/projects/ugandaemr/files/1.0.15/ugandaemr1-0-15-installer-32.exe/download
4. 64 bit installer - https://sourceforge.net/projects/ugandaemr/files/1.0.15/ugandaemr1-0-15-installer-64.exe/download

### Recommended Upgrade Paths depending on existing UgandaEMR version 
1. 1.0.14 - Replace the WAR file with a new one 
2. 1.0.13-SNAPSHOT - Replace the WAR file with a new one 
2. 1.0.12 and lower versions 
  - Run the concept script from https://sourceforge.net/projects/ugandaemr/files/1.0.13/concept_dictonary_ref_1.0.13.sql/download
  - Deploy the WAR file 






  