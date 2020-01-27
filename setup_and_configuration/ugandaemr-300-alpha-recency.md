

# UPGRADING TO UGANDAEMR VERSION 3.x-alpha-recency



##### 1.	Back up UgandaEMR

Log into UgandaEMR, on the main page, click Back up.  
On the next page that opens, click “Execute database backup now”.  
Wait until backup completes and shows the message “Backup complete”



##### 2.	Back up installation files

Navigate to: C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\  
Back up the file openmrs.war. \(This is the stable version you found on the system. You can back it up by copying openmrs.war file to the Desktop and rename to openmrs-previous.war\)



##### 3.	Start the EMR upgrade

#### From UgandaEMR version 2.0

First upgrade version 2.0 to version 2.1. Use the upgrade installer located [here](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr_upgrade_from_2.0.0_to_2.1.0_64bit.exe/download). This will upgrade the EMR to version 2.1. For full process, refer to the release notes for version 2.1 on the UgandaEMR portal. After the upgrade process to 2.1, you can then continue with the steps below.

#### From UgandaEMR version 2.1

###### a. Stop UgandaEMR

- Search for tomcat on the windows start menu and click it. Click “yes” if requested confirmation.   
- Double click the system tray tomcat manager icon   
- In the tomcat manager widow that opens, click “Stop”.   
- Wait until UgandaEMR stops completely – that is when the “Start” button becomes enabled.

###### b. Delete file C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\openmrs.war

###### c. Delete folder C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\openmrs\

###### d. Delete folder C:\Program Files\UgandaEMR\UgandaEMRTomcat\work\Catalina\localhost\openmrs\

###### e. Paste the new openmrs.war file you have into the folder C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\

###### f. Start UgandaEMR. Use tomcat manager shown in \(a\) above, click “Start” and browse UgandaEMR.

###### g. Reset reports. To do this, follow the steps in the known issue

###### h. Restart the computer

  

#### Known Issues

##### 1.	Reports Issue

This has been observed when upgrading from UgandaEMR 2.0 to 3.x. Signs of this issue include:

###### Symptoms:

- Reports may not display at all, or they may not be showing as expected.  
- The server does not fully start up and the log files show an error related to reports module . It may mention “excel” in the log file located in `C:\Program Files\UgandaEMR\UgandaEMRTomcat\logs\ugandaemrtomcat-stdout….log`

###### Resolution

Reset all reports by running the following SQL commands.

a - Open Heidi application by searching it from windows start menu.   
b - In the window that opens, click “New”  
c - Enter the login credentials to the database. In the field “User” enter openmrs. Enter the password and Click Open.  
d - In the left part of the window, Click on openmrs   
e - Open the menu “File -&gt; New query tab”. In the window that opens, paste the following 

```
DELETE FROM reporting_report_design_resource;
DELETE FROM reporting_report_design;
DELETE FROM global_property WHERE property LIKE 'reporting.reportManager%';
DELETE FROM serialized_object WHERE type LIKE 'org.openmrs.module.reporting.report%';
```

f - Select one line at a time, right click and click on “Run selected”. If prompted, with a warning message, click “yes” to continue.



##### 3.	Reports module does not start or stay started

###### Symptoms:

- Reports module may start when all modules are started manually but does not start when computer restarts  
- The stdout log file will contain this message, `“PacketTooBigException: Packet for query is too large”`

###### Resolution

a.	Open the "my.ini" file under `C:\Program Files\UgandaEMR\MySQL` folder. Note that this file may just appear as “my” without the file extension. Do not modify any other file.  
b.	Search for the "max\_allowed\_packet" parameter. If the file does not have it, add the parameter to the file.  
c.	To add the parameter, enter the following value in its own line: `max_allowed_packet=5G`

d.	Restart the computer.

  

## CHECK LIST



1	Did the backup complete successfully?		  
2	On the login page, does the UgandaEMR version show Ver 3.0.0-alpha-recency-x?		  
3	Are all the following modules turned on?  
    a. UgandaEMRPOC   
    b. Aijar  
    c. Database Backup Module  
    d. UgandaemrSync  
    e. Reporting		

4	Was the “Dhis2 organisation uuid” for this facility entered in settings?		  
5	Was the “Hts recency” value set to “true” in the settings?		  
6	Was the “Recency Server URL” entered in settings?		  
7	Was the “Recency Server Password” entered in settings?		  
8	Was the computer restarted after all configurations were done?		  
9	Do you see the recency question in the HTS client card?	  
10   Were the report fixing steps outlined in the "Known issues" run?

