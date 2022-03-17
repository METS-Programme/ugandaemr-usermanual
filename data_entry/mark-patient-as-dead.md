## Mark Patient as Dead

To mark patient as dead, you will have to log into one of the clinics, i.e. SMC, ART, TB, MCH, OPD, Lab.

An example is; SMC;  login at the "SMC clinic" session, as shown below.  
![](SMC12.png)

A screen will open as shown below. Select the "Find Patient Record" option.  
![](SMC11.png)

On the screen that appears, type the name or ID of the patient, as registered in the system.  
![](SMC13.png)

Search for and find the client - Demo 123  
![](/images/terminated1.jpg)

![](/images/terminated%202.1.PNG)![](/images/terminated%2031.PNG)

![](/images/terminated%204.PNG)

![Patient Marked as Dead](/images/terminated%205.PNG)

### Troubleshooting Tips 
#### I am unable to mark a patient as dead - no error appears and nothing is shown 

This problem has been identified with migrations from older versions of OpenMRS where some data is empty which causes internal validation issues

1. Backup your database 
2. Open a command prompt and type the following commands:

  `mysql --verbose --verbose -u openmrs -popenmrs -e "DELETE FROM person_attribute WHERE value IS NULL OR value = '';" openmrs`
2. The output of the command will be similar to: 
  `Warning: Using a password on the command line interface can be insecure.
  \--------------
DELETE FROM person_attribute WHERE value IS NULL OR value = ''
  \--------------

  Query OK, 1359 rows affected (0.18 sec)`
3. Backup your database 
4. Try marking a patient as dead, the issue should be resolved 

