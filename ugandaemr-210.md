## UgandaEMR 2.1.0 Release Notes
Currently work in progress 

### New Features

1. Patient Flags - these allow highlighting information on the patient dashboard following the traffic light coloring, green (good), orange (take note), red (take action). The summary of flags by color codes are:
   * Green - Upcoming Appointment, Due for First Viral Load, Due for Routine Viral Load, Due for 1st DNA PCR, Due for 2nd DNA PCR, Due for Rapid Test
   * Orange - Missed Appointment, 
   * Red - Overdue for First Viral Load, Overdue for Routine Viral Load, Lost, Lost to Followup, Overdue for 1st DNA PCR, Overdue for 2nd DNA PCR, Overdue for Rapid Test, Has Detectable Viral Load

2. Differentiated Service Model
   * All patients enrolled in HIV care are placed in the FBIM model 
   * During the data capture for an ART Encounter the model can be changed 
   * Only stable patients can be moved to community models 
   * The history of the patient's models is displayed on the patient's dashboard 
   * A report showing the current model for all patients has been added 

3. Patient Dashboard
   * Summary from Last Visit 
   * Viral Load Summary 
4. 
5. Reports

  * Facility Reports 
  * MER Indicator Reports - TX_CURR (for 30 days and 90 days), TX_NEW, TB

### Bug Fixes

1. Data quality violations were not removed when cleared 
2. ART Summary page would not save with some dates 

### Links to download files

This release requires a re-installation of UgandaEMR due to an internal platform change that requires Java 8, instead of Java 7 that was used by previous versions. However separate files are provided for new installations and upgrades 

#### WAR File 


#### New Installation

For new machines with no UgandaEMR installed

1. 32 bit installer (TBD) - 
2. 64 bit installer (TBD) -  


#### Upgrade Installer 

For existing versions of UgandaEMR 1.x 

1. 32 bit upgrade installer (TBD) - 
2. 64 bit upgrade installer (TBD) -  

