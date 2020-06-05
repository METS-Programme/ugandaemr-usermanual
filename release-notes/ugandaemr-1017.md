# 1.0.17

## Bug Fixes

1. ART Summary Page
   * Validation rules for ART start date, HIV enrolled dates and Transfer In
2. Exposed Infant Summary Page
   * Removed required field for next appointment date which is not available in multiple cases 
3. Data entry statistics module added 
4. New version of database backup module with:
   * support for large installations which were stopping at the obs table 
   * More efficient data export to speed up imports 

## New Features

None

## Links to download files

1. WAR file - [https://sourceforge.net/projects/ugandaemr/files/1.0.17/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/1.0.17/openmrs.war/download)
2. 32 bit installer - [https://sourceforge.net/projects/ugandaemr/files/1.0.17/ugandaemr1-0-16-installer-32.exe/download](https://sourceforge.net/projects/ugandaemr/files/1.0.17/ugandaemr1-0-16-installer-32.exe/download)
3. 64 bit installer - [https://sourceforge.net/projects/ugandaemr/files/1.0.17/ugandaemr1-0-16-installer-64.exe/download](https://sourceforge.net/projects/ugandaemr/files/1.0.17/ugandaemr1-0-16-installer-64.exe/download)

## Recommended Upgrade Paths depending on existing UgandaEMR version

1. 1.0.14 and 1.0.16 - Replace the WAR file with a new one following the steps at [Upgrading with a WAR file](../upgrading/#upgrading-with-a-war-file)
2. 1.0.13-SNAPSHOT - Replace the WAR file with a new one 
3. 1.0.12 and lower versions 
   * Run the concept script from [https://sourceforge.net/projects/ugandaemr/files/1.0.13/concept\_dictonary\_ref\_1.0.13.sql/download](https://sourceforge.net/projects/ugandaemr/files/1.0.13/concept_dictonary_ref_1.0.13.sql/download)
   * Deploy the WAR file 

