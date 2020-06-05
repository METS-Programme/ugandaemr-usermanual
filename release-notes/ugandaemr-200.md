# 2.0.0

This release mainly focused on upgrading to the OpenMRS 2.x platform which runs on Java 8 on which all Reference Application releases from 2.6.0 will be based. This upgrade provides a stable foundation for future upgrades

## New Features

1. New Data collection forms
   * Antenatal, Maternity and Postnatal data collection forms based on the register  
   * Tuberculosis - matching the longitudinal register 
   * Outpatient Register from based on the register 
2. Exposed Infant Form
   * Children are automatically linked to their mothers through the mother's ART number 
3. Patient Dashboard
   * Sticky note \(yellow\) that allows you to enter notes on the patient 
   * New widgets to show Exposed Infant and ART status 
   * Links to family members 
   * Data quality violations shown 
4. Data Quality
   * Ability to filter the rules by patient and rule type 
   * New validation rules for Exposed Infants - infants without mother's ART number, infants with mother ART number but not linked
5. Reports
   * ANC, Maternity and PNC registers 
   * Exposed Infant reports to aid facility tracking and planning 

## Bug Fixes

None

## Links to download files

This release requires a re-installation of UgandaEMR due to an internal platform change that requires Java 8, instead of Java 7 that was used by previous versions. However separate files are provided for new installations and upgrades

### New Installation

For new machines with no UgandaEMR installed

\*32 bit installer \(469.6MB\) - [https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr2-0-0-installer-32.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr2-0-0-installer-32.exe/download)

* 64 bit installer \(478.1 MB\) - [https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr2-0-0-installer-64.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr2-0-0-installer-64.exe/download)

### Upgrade Packages

For existing versions of UgandaEMR

* 32 bit upgrade installer \(206.0 MB\) - [https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr\_2.0\_upgrade32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr_2.0_upgrade32bit.exe/download)
* 64 bit upgrade installer \(206.0 MB\) - [https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr\_2.0\_upgrade64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/2.0.0/ugandaemr_2.0_upgrade64bit.exe/download)

