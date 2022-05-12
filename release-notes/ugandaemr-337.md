# 3.3.7 - April 2022 

## New Features

1. Martnernal and Child Health
  
   * Antenatal  Services for both Point of Care and Restrospective approach. 
   * Maternity Services
   * Postnatal Services
   * Reports - (105 MCH Section, ANC 105, Marternity 105, 105 PNC )
   
2. Safe Male Circumcision - Retrospective Data Entry for SMC Services
    
3. Create a generic approach to generating  and Sync FHIR Encounters for data exchange
4. Added Missing Districts [Arua city,Jinja city, Lira city, Masaka city,Mbale city, Mbarara city, Soroti city]
    
## Improvements
 
 1. Added display board for logs
 2. Added SNOMED CT Mapping to Fhir Concept Source Table
 3. Removed dependency on guava that is flagged as a potential security issue
 4. Fixed the checking of results in order to also check for results entered from the encounter
 5. Ensure that orders with Viral Load results are completed.
 6. Improve viral load  Non Suppressed form Validation Rules
 7. Update Transfer-In Regimen to match the list of regimens in current regimen
 8. Differentiate between a pharmacy visit and a facility visit in ART Access on Patient Dashboard
## Bug Fixes 

1. Fixed failing retrospective of Ordering Viral Load
2. Fixed appointments widget with some appointments not showing.
3. Made return visit mandatory, transfer out and location required when patient is transferred out

## Links to download files

### New Installation

For new machines with no UgandaEMR installed

* 32-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.3.7/ugandaemr3-3-7-installer-32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.7/ugandaemr3-3-7-installer-32bit.exe/download)
* 64-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.3.7/ugandaemr3-3-7-installer-64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.7/ugandaemr3-3-7-installer-64bit.exe/download)

### WAR File

[https://sourceforge.net/projects/ugandaemr/files/3.3.7/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/3.3.7/openmrs.war/download)

### Upgrade Installer

**For existing versions of UgandaEMR 2.0.x to 3.3.7**
Upgrade to 3.3.0 using the following scripts. 

* 32-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr\_upgrade\_from\_2.0.x\_to\_3.3.0\_32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr_upgrade_from_2.0.x_to_3.3.0_32bit.exe/download)
* 64-bit upgrade files- [https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr\_upgrade\_from\_2.0.x\_to\_3.3.0\_64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.3.0/ugandaemr_upgrade_from_2.0.x_to_3.3.0_64bit.exe/download)

Then upload the war file for 3.3.7. 


## Fixing Failed Installations and Upgrades

None