## Troubleshooting Tips

This section contains tips and tricks to help maintain your installation, as well as a general guide to common problems 

### My installation cannot start 
Restart your computer

### UgandaEMR login screen not available yet system starts
**Error Messages and Screenshots ** 
![Login Error no modules started](images/login_error_modules_not_started.png)

When you login the screen may display as below:

![Modules not started errors](images/module_not_started_error-1.jpg)

![Modules not started due to cyclic dependencies](images/module_not_started_error_2.png)

**Resolution**

1. On the Administration page, select the Manage Modules link
![Manage Modules](images/manage_modules_link.png)
2. Click the Start All button 
![Start All Modules](images/modules_start_all.png)
3. Restart your computer 

### OpenMRS cannot start - Error creating bean with name "messageSourceServiceTarget"

**Error Messages and Screenshots**

![OpenMRS cannot start - Error creating bean of name "messageSourceServiceTarget"](images/error_message_source.jpg) 

** Resolution ** 

1. Delete the folder C:\Application Data\OpenMRS\lucene
2. Restart your computer 

### White screen appears when carrying out administrative tasks like module installation, upgrade 