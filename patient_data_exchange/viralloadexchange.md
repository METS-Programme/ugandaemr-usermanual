## VIRAL LOAD DATA EXCHANGE

### Introduction
The Viral Load exchange involves the sending of a request to CPHL and receiving the results back in the UgandaEMR at the health center.  The sending of a viral load request requires user involvement in the capacity of clinical and Laboratory personnel.  

This guideline aids UgandaEMR users on how to configure and use the viral load Health information exchange. 

###Configuration
In order to enable exchange of viral load exchange between CPHL and the health center, credentials to access the CPHL Viral Load system are required. The username and password will be provided in different channels. Once obtained, the steps to setup the username and password are as follows:

1. Login in UgandaEMR with an account that has  administrator rights to the system. This will navigate you to the home page of UgandaEMR. 

2. Click on the ” System Administrator” Icon. This will navigate you to the System Administrator Page.

3. Click on the “UgandaEMR Sync '' Icon. This will navigate you to the ugandaemr sync settings page. 

4. Click on the “Sync Task Type” icon. This will navigate you to the Sync task Type Config Page. With a table showing the different exchange settings.

5. On the list item named “Send Viral Load To CPHL” Click on the edit icon under the “ACTION” column. This will popup a dialogue box.

6. In the dialogue box enter the username and password provided in the respective fields.

7. Click on the “save” button to save the changes.

8. On the list item named “Request Viral Load Results form CPHL” Click on the edit icon under the “ACTION” column. This will popup a dialogue box.
Repeat Step 6 and 7.


### Clinician actions for exchange of viral load
The Clinician orders for the viral load that the lab has to process and send to CPHL. In order for the clinician to order for a viral load test, they must have a role “HIV Clinic”. Then they have to carry out the following steps to order for a viral load test:

1. Login UgandaEMR using a username and password with “HIV Clinic” role. This will navigate you to the “home page” of UgandaEMR. 

2. Click on the “ART Clinic” icon. This will navigate you to a list of patients in different tabs. That is “Patient New” tab, “Patients - Lab results” tab and “Patients - Attended To” tab.

3. In the “Patient New” tab, in the “ACTION” column, Click on the patient dashboard icon . This will navigate you to the patient dashboard. 

4. On the right side under the “Current Visit Actions”, Click on the “HMIS 003 HIV Care ART Card - Clinical Assessment”. This will navigate you to the Clinical assessment form. This contains a number of tabs and sub tabs 

   a).  **Clinical Encounter tab**.  This tab has the following sub-tabs. 
        
    Triage Information. This contains information that has been captured from triage
    
    Pregnancy/Family Planning tab.This fields that are used to capture information on family planning of a patient. 

    Examinations Tab has fields to capture information on Presenting Signs and Symptoms , Advanced Disease and WHO Clinical Stage, Side Effects Of ART, TB AND TPT and Syphilis status
    
    Investigations. This tab contains fields that are used to order for tests in the lab. It is in this section where tests such as viral load can be ordered in order for them to be processed by the lab technician.
   
   b).  **Investigation Report.** This tab contains information on investigation results that have been done in the lab. It contains two sub tabs that is

    Report. This displays any result that has been sent back to the clinician by the lab 
    
    Capture Results. This has the results fields for essential tests in the HIV clinic. A Clinician can capture the results on the patient records from here
  
    c) **Diagnosis.** The Diagnosis tab contains a field that allows one to capture diagnosis of a patient. The field is an autocomplete field where you have to type at least two to three characters to show the alternatives one can select on. The select field can be selected as a primary and secondary diagnosis.
    **Please Note:** At least one primary diagnosis required when the diagnosis field is used.
    
    d) **Medication**. This Tab contains all medication options that can be ordered for a patient.
    **Please Note:** Any Medication selected in this section will result in a pharmacy request to the dispensing personnel.
    
     e) **Programming Tab** . This Tab contains the DSDM programming and duration on ART.
    
    f) **Next Course of action.** This Tab contains fields that are used to schedule the next appointment, or transfer out a patient.

 5. In the “Clinical Encounter”  tab under the “Investigations” sub tab in the “Laboratory Tests” section, Check the viral load checkbox. 
 
 6. Complete any other information that the patient session requires if any. 
 
 7. Click on the save button on the left. This will navigate you back to the patient dashboard. At this moment the viral load request has been sent to the laboratory for bleeding and processing the sample.

### Lab Personnel actions for exchange of Viral Load. 

When the clinician has ordered for a viral load request as a test, The personnel with the “Organizational: Laboratory” role will be able to process the sample and send a request to CPHL in the following steps. 

1. Login in UgandaEMR with an account that has the role “Organizational: Laboratory”. This will navigate you to the “home page” of UgandaEMR.

2. On the Home page, Click on the “Laboratory” icon. This will navigate you to the laboratory dashboard with “Test Ordered” tab, “Worklist” tab, “Referred tests” tab, and “Results” tab 

3. Under the “Test Ordered” tab in the “TEST(S) ORDERED” column, Click on the “Tests Unprocessed” link. This will dropdown the ordered tests of patients.

4. In the ordered test list provided, Click on the “process sample”  icon . This will popup a dialogue box to enable you to process the sample.  

5. Enter the sample/specimen Id in the textbox provided. 
**Please Note:** The serial number on the form which will be sent to CPHL is the number that has to be entered in the specimen id placeholder.

6. Select the specimen type in the dropdown provided. 
7. Check the “REFER TEST” checkbox. This will show a dropdown with different options of referral of test in a select named “Select Reference Lab”. 
8. Select the option “CPHL”. 
9. Click on the “Send” button. This will move the test from the  “Test Ordered” to the worklist. At this moment the test has been processed and ready to be sent to CPHL when synchronization occurs in the background.  

### How to Receive the result back from CPHL
The results will be automatically pulled by UgandaEMR when a result is availed by the CPHL dashboard. This process does not require the user  to interact with the system. Requires active internet connection.


