# Patient Registration

## Patient Registration

1.Login and on the home page click the Find Patient Link circled below

![Register Patient Link](../.gitbook/assets/poc_find_patient_link%20%281%29.png)

2.In the Search Bar, type any patient identifiers to search for the patient, if no results are returned, click the Create new Patient link as shown below. ![Patient Search Bar](../.gitbook/assets/poc_search_bar%20%281%29.PNG)

3.On clicking Create New Patient, you enter patient details as below;

3.1._Patient Name_![PatientName](../.gitbook/assets/name%20%281%29.png)  
3.2._Gender_ ![Gender](../.gitbook/assets/gender%20%281%29.png)  
3.3._Birth date_ ![Birthdate](../.gitbook/assets/birth_date%20%281%29.png)  
3.4._Marital Status_![Marital Status](../.gitbook/assets/marital_status%20%281%29.png)  
3.5._Birth Location_ aka village in which patient was born![birthlocation](../.gitbook/assets/birth_location%20%281%29.png)  
3.6.\*Address: Where the patient lives. Please follow the same procedure as above

3.7._Phone Number: \_\__\_\__\_\_  
3.8.\_ Next of Kin: ![Next of Kin](../.gitbook/assets/next_of_kin%20%281%29.png)

3.9.\* Confirm: Shows all the bio-data collected about the patient.![Confirm](../.gitbook/assets/confirmation%20%281%29.png)  
3.10. Saving The data: Click confirm to save, if not click cancel to edit. You should see a patient registration summary once saving is successful as below ![](../.gitbook/assets/poc_patient_summary%20%281%29.PNG)

## Editing Patient Registration Information

1.Login and on the home page click the Find Patient Link circled below

![Register Patient Link](../.gitbook/assets/poc_find_patient_link%20%281%29.png)

2.In the Search Bar, type any patient identifiers to search for the patient, the record of the patient appears as shown below.

![Patient Search Record](../.gitbook/assets/poc_patient_record_search.png)

3.Click on the last action that has Edit Demographics as shown below;

![Edit Patient Demographics](../.gitbook/assets/poc_edit_patient_demographics.png)

4.Edit Patient Information by clicking on the pencil icon next to a section header where those details belong

![Registration Summary](../.gitbook/assets/poc_registration_summary.PNG)

5.Confirm the details and Save the information.

## Merging Patients

Patient Merging in UgandaEMR refers to the act of “retiring” Patient B in favour of patient A. In such an event, the visits, encounters, observations and other underlying objects which belonged to patient B will be transferred to Patient A, and Patient B will be retired. In a multiple patient merge process, Patients A, B and C may be retired in favour of patient X. Patient Merging is useful in situations where duplicate records have been created for a single patient.

**Note:** Patient merging is uni-directional only. It does not allow the restoration of merged data i.e. you cannot reverse the process. Therefore patient merging shouldn’t be taken lightly and effected only if you are **100%** sure that the patients are the same.

To merge patients;

1. Login as a user with administrator privileges and click the “_Legacy System Administration_” link as shown in the image below. ![Legacy System Administration](../.gitbook/assets/patient_merge1%20%281%29.png)
2. Click on the _“Find Patients to Merge_” link as shown below.

   ![Find Patient to Meger](../.gitbook/assets/patient_merge2%20%281%29.png)

3. Select a minimum of two patient attributes to search on and click _“search”_ as shown in the image below.

   ![Search Patient](../.gitbook/assets/patient_merge3%20%281%29.png)

4. This displays a list of patients who match the attirbutes used in the search. Select two or more patients to continue.

   ![Patient List](../.gitbook/assets/patient_merge4%20%281%29.png)

5. Select your preferred patient to keep and click _“Merge Patients”_ button to continue

   ![Merge Patient](../.gitbook/assets/patient_merge5%20%281%29.png)  
   The "Preferred Patient" is the patient who "survives" in favour of the retired patient.

6. A Dialog box displays asking you to confirm the Merge. Click “Ok” to confirm and complete the patient merging process or "Cancel" to abort the process.

   You should see a notification indicating that the process was completed successfully.

   ![Complete Patient Merge](../.gitbook/assets/patient_merge6%20%281%29.png)

## Marking Patients as Dead

1.To mark patient as dead, you will have to log into one of the clinics, i.e. SMC, ART, TB, MCH, OPD, Lab.

An example is; SMC; login at the "SMC clinic" session, as shown below.  
![SMC Clinic](../.gitbook/assets/SMC12.png)

2.A screen will open as shown below. Select the "Find Patient Record" option.  
![Find Patient](../.gitbook/assets/SMC11.png)

3.On the screen that appears, type the name or ID of the patient, as registered in the system.  
![Patient ID](../.gitbook/assets/SMC13.png)

4.Search for and find the client - Demo 123  
![Patient Example](../.gitbook/assets/terminated1%20%281%29.jpg)

![Mark Patient Deceased](../.gitbook/assets/terminated%202.1.PNG) ![Check Patient Deceased](../.gitbook/assets/terminated%2031.PNG)

![Save Changes](../.gitbook/assets/terminated%204.PNG)

![Patient Marked as Dead](../.gitbook/assets/terminated%205.PNG)

## Marking a Dead Patient as alive

TBD

## Common Errors

### User is not a provider

![User Not Provider Error](../.gitbook/assets/logged_in_user_not_provider%20%281%29.png)

#### Solution

The above means your User Account does not have privileges to provide care to a patient. You therefore have to add Provider role to the user account as [indicated herein](../provider_management/making_an_existing_user_a_provider.md)

### Failed to save changes during patient registration

![Failed to save changes](../.gitbook/assets/user_registration_failed_to_save_changes%20%281%29.jpeg)

#### Solution

This problem is common with implementations that have been upgraded from 1.6.3 and is caused by null or empty string values for patient attributes during migrations.

The solution is as follows:  
1. Backup your database  
2. Run the following command:

`DELETE FROM person_attribute WHERE value IS NULL OR value = '';`

**For Version 2.1.0 and above**

1. Download a script from [https://sourceforge.net/projects/ugandaemr/files/2.1.0/scripts/clear\_edit\_error.sql/download](https://sourceforge.net/projects/ugandaemr/files/2.1.0/scripts/clear_edit_error.sql/download)
2. Go to start menu and search for Execute Mysql Script and click on it. This will pop up a dialog window
3. Click install. This will prompt you to select a file. 
4. Select the Download file and click okay.
5. Restart Computer.

