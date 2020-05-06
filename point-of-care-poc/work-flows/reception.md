### Reception Workflow
The Receptionist requires a role called "Reception" which allows one to perform the following roles
#### [Search for patient](To be determied)
#### [Register a patient](../../patient_registration.md)
#### [Edit patient demographics](../../patient_registration.md)
#### Check in patient
In Order to check in a patient, a patient the user with _"reception"_ role must follow these steps
1. [Login](To be determied) with account that has [role](../installation-and-configuration/roles.md) reception. This action will navigate you to the home screen. 
![Home Screen](../../assets/poc_find_patient_link.png)
2. On the Home Screen Click on the _"Find patient record"_ icon this will navigate you to the _"patient search"_ page.
![Search Page](../../images/poc/poc_search_patient_page.png)
3. In the search box provided, type patient names or identifier. This will show a drop down list of patient (s) who match the typed details.
**Note:** In case you need guidelines on searching by fingerprint refer to [This Link](To be determied)
![Search Page](../../images/poc/poc_patient_in_search_list.png)
4. In the the Action column in the search list on a patient item, click on the ![checkin icon](../../images/poc/poc_checkin_icon.png). This should show a check in  dialogue popup
![Check in popup](../../images/poc/poc_check_in_popup.png)
By Default the Checkin popup has two fields
    
        a ) Entry Point. This is the Clinical point in which the patient has shown up at the health center for example HIV Clinic, OPD Clinic, MCh Clinic........
        b )  Next Service Point. This is whene you would like to send a petient to.
5. Select the Entry point and the Next Service point. This will show a checkin tocken print out which may be printed out and given to the patient.

      ![Check in popup](../../images/poc/poc_check_in_token.png). 
At this moment the patient is checked in and in the queue you selected as the _"next service point"_
   