## Patient Registration and Management

### Patient Registration

1.Login and on the home page click the Register patient link circled below

![Register Patient Link](images/register_patient_link.png)
2.Enter the details of the patient ensuring that the required fields which are marked with \* are entered

3.On clicking the Register Patient icon, you enter patient details as below;

3.1._Patient Name_![PatientName](images/name.png)
3.2._Gender_ ![Gender](images/gender.png)
3.3._Birth date_ ![Birthdate](images/birth_date.png)
 3.4._Marital Status_![Marital Status](images/marital_status.png)
 3.5._Birth Location_ aka village in which patient was born![birthlocation](images/birth_location.png)
 3.6.\*Address: Where the patient lives. Please follow the same procedure as above

3.7._Phone Number: \_\__\_\__\_\_
3.8._ Next of Kin: ![Next of Kin](images/next_of_kin.png)

3.9.\* Confirm: Shows all the bio-data collected about the patient.![Confirm](images/confirmation.png)
3.10. Saving The data: Click confirm to save, if not click cancel to edit. You should see a patient dashboard once saving is successful as below ![](images/patient_dashboard.png)

### Merging Patients

Patient Merging in UgandaEMR refers to the act of “retiring” Patient B in favour of patient A. In such an event, the visits, encounters, observations and other underlying objects which belonged to patient B will be transferred to Patient A, and Patient B will be retired. In a multiple patient merge process, Patients A, B and C may be retired in favour of patient X. Underlying objects which belonged to patients A, B and C will also be transferred to patient X as specified earlier.

**Note:** Patient merging is uni-directional only. It does not allow the restoration of merged data i.e. you cannot reverse the process. Therefore patient merging shouldn’t be taken lightly and effected only if you are **100%** sure that the patients are the same.

To merge patients;

1. Login as a user with administrator privileges and click the “_Legacy System Administration_” link as shown in the image below.
  ![](/assets/patient_merge1.png)

1. Click on the _“Find Patients to Merge_” link as shown below.

  ![](/assets/patient_merge2.png)


2. Select a minimum of two patient attributes to search on and click _“search”_ as shown in the image below.

  ![](/assets/patient_merge3.png)
3. This displays a list of patients who match the attirbutes used in the search. Select two or more patients to continue.

  ![](/assets/patient_merge4.png)
4. Select your preferred patient to keep and click _“Merge Patients”_ button to continue

  ![](/assets/patient_merge5.png)
  The "Preferred Patient" is the patient who "survives" in favour of the retired patient.

5. A Dialog box displays asking you to confirm the Merge. Click “Ok” to confirm and complete the patient merging process or "Cancel" to abort the process.

  You should see a notification indicating that the process was completed successfully.

  ![](/assets/patient_merge6.png)

### Marking Patients as Dead

TBD

### Marking a Dead Patient as alive

TBD

### Common Errors

#### User is not a provider

![User Not Provider Error](images/logged_in_user_not_provider.png)

### Solution:

The above means your User Account does not have privileges to provide care to a patient. You therefore have to add Provider role to the user account as [indicated herein](making_an_existing_user_a_provider.md) .

