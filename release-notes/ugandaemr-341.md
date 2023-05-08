# 3.4.1 - May 2023 

## New Features

1. **Stock Management & Dispensing Module (SMD)**
   * The module supports the documentation of all medical supplies distributed and/or received at health facility from the national medical warehouses. 
   * At the stores, the store manager/officer receives and takes stock of the medical supplies; And the Facility pharmacy can make requests to the store.
   * The module supports the clinical workflow of drug prescription and dispensing at a health facility.
<!-- -->
2. **Facility Dashboards** 
   * Real-time dashboards for key performance indicators (KPI) for improved data use through visualization such as;
     * Comprehensive dashboards on care and treatment.
     * Comprehensive dashboards covering the entire  HTS cascade.
     * Comprehensive dashboards for appointments including weekly appointment's coverage.

<!-- -->
3. **SMS Patient Reminders** 
   * Enrolling patients into the SMS program to receive reminders of their upcoming facility visit / appointment.
   * Customization of facility messages sent out to the patients.
   * Provide a list of all patients enrolled on the SMS program.
   * Deregister a patient from the SMS program

<!-- -->
4. **Client Registry**
   * An integration between UgandaEMR and the National  MOH client registry to exchange data between the UgandaEMR and the client registry for patient Identification and deduplication.

<!-- -->
5. **NextGen Reporting**
   * Functionality to generate MER and HMIS reports and submit them directly to the respective national reporting systems.

## Bug Fixes & Improvements 
1. **HIV Testing Services (HTS)**
   * Redesigned the HMIS 018ACP: HTS Client Card to simplify the process of data entry.
   * Added the missing fields in the HMIS 105 HTS Section report.
   * Added Number of days since last tested and place last tested to the client card.
   
<!-- -->
2. **Viral Load Exchange (VL)** 
   * Sending VL request form from UgandaEMR to CPHL

<!-- -->
3. **Tuberculosis Preventive Therapy (TPT)** 
   * TPT Start & Completion dates displayed on subsequent ART Encounters once they are captured.
   * TPT Completion status captured once and displayed on subsequent encounters (Non-repetitive capture).

<!-- -->
4. **Patient Demographics - Address Hierarchy** 
   * Addition of new cities, districts, counties, sub counties, parishes and villages to the address fields inline with the country’s administrative units.

<!-- -->
5. **HIV - TB Linkage**
   * ART Information visible on TB Enrollment and Follow-up encounters.
   * TB Information displayed on ART Encounters once a client is enrolled into the TB program.

<!-- -->
6. **ART Access Integration**
   * Differentiating between Facility visit and pharmacy visit.

<!-- -->
7. **DSDM Categorization**
   * Added functionality to sub-categorize CCLAD clients into different CCLAD groups.
   * Added functionality to sub-categorize CDDP clients into General CDDP groups.

<!-- -->
8. **SMC Enhancements**
   * Allow Logicane Batch Number filled to take in alphanumeric values not just integers

## Links to download files

### New Installation

For new machines with no UgandaEMR installed

* 32-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.4.1/ugandaemr3-4-1-installer-32bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.4.1/ugandaemr3-4-1-installer-32bit.exe/download)
* 64-bit installer -[https://sourceforge.net/projects/ugandaemr/files/3.4.1/ugandaemr3-4-1-installer-64bit.exe/download](https://sourceforge.net/projects/ugandaemr/files/3.4.1/ugandaemr3-4-1-installer-64bit.exe/download)

### WAR File

[https://sourceforge.net/projects/ugandaemr/files/3.4.1/openmrs.war/download](https://sourceforge.net/projects/ugandaemr/files/3.4.1/openmrs.war/download)

