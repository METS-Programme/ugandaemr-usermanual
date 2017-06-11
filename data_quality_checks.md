# Data Validation 
Currently data validation rules are enforced on the data entry forms to ensure that required information is entered and that conflicting data items are not entered e.g., pregnancy for males. 

The following data quality checks are available in UgandaEMR starting from [version 1.0.16](ugandaemr-1016.md)
 under different rules:

1. Incomplete ART information
  * Patients on ART without ART start date 
  * Patients on ART without an ART start regimen 
  * Patients on ART with other regimen - this was common where the regimens were not added, so now the need is to move all patients with other to the respective regimen to improve computation of patients on first and second line
2. Invalid ART encounters
  * Patients on ART with summary page and no encounters 
  * Patients on ART with encounters but no summary page
  * Patients with more than one ART summary page 
  * Patients with more than one encounter of the same type on the same date 
3. Incomplete Exposed Infant Information 
  * Exposed Infants with Summary page and no encounters 
  * Exposed Infants with Encounters and no Summary page 
  * Exposed Infants older than 18 months with no final outcome 


