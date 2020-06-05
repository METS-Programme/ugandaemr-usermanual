# UgandaEMR 3.x Installation

## UgandaEMR 3.x Upgrade

1. Back up UgandaEMR
   * Log into UgandaEMR, on the main page, click Back up.  
   * On the next page that opens, click “Execute database backup now”.  
   * Wait until backup completes and shows the message “Backup complete”
2. Back up installation files
   * Navigate to: `C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\`  
   * Back up the file openmrs.war \(This is the stable version you found on the system. You can back it up by copying openmrs.war file to the Desktop and rename to openmrs-previous.war\)
3. Start the EMR upgrade a\) Upgrade from UgandaEMR version 2.0

   * First upgrade version 2.0 to version 2.1. Use the upgrade installer located [here](https://sourceforge.net/projects/ugandaemr/files/2.1.0/ugandaemr_upgrade_from_2.0.0_to_2.1.0_64bit.exe/download). This will upgrade the EMR to version 2.1. For full process, refer to the release notes for version 2.1 on the UgandaEMR portal.   
   * After the upgrade process to 2.1, you can then continue with the steps below.

   b\) From UgandaEMR version 2.1

   * Stop UgandaEMR
   * Search for tomcat on the windows start menu and click it. Click “yes” if requested confirmation.

4. Double click the system tray tomcat manager icon
5. In the tomcat manager widow that opens, click “Stop”.
6. Wait until UgandaEMR stops completely – that is when the “Start” button becomes enabled.

b. Delete file C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\openmrs.war

c. Delete folder C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\openmrs\

d. Delete folder C:\Program Files\UgandaEMR\UgandaEMRTomcat\work\Catalina\localhost\openmrs\

e. Paste the new openmrs.war file you have into the folder C:\Program Files\UgandaEMR\UgandaEMRTomcat\webapps\

f. Start UgandaEMR. Use tomcat manager shown in \(a\) above, click “Start” and browse UgandaEMR.

g. Reset reports. To do this, follow the steps in the "Reports known issue" below

h. Restart the computer

## Known Issues and Troubleshooting Tips

### Reports links do not display

This has been observed when upgrading from UgandaEMR 2.0 to 3.x. Signs of this issue include:

**Symptoms:**

1. Reports may not display at all, or they may not be showing as expected.  
2. The server does not fully start up and the log files show an error related to reports module . It may mention “excel” in the log file located in `C:\Program Files\UgandaEMR\UgandaEMRTomcat\logs\ugandaemrtomcat-stdout….log`

**Resolution**

Reset all reports by running the following SQL commands.

1. Open Heidi application by searching it from windows start menu.  
2. In the window that opens, click “New”  
3. Enter the login credentials to the database. In the field “User” enter openmrs. Enter the password and Click Open.  
4. In the left part of the window, Click on openmrs  
5. Open the menu “File -&gt; New query tab”. In the window that opens, paste the following

```text
DELETE FROM reporting_report_design_resource;
DELETE FROM reporting_report_design;
DELETE FROM global_property WHERE property LIKE 'reporting.reportManager%';
DELETE FROM serialized_object WHERE type LIKE 'org.openmrs.module.reporting.report%';
```

1. Select one line at a time, right click and click on “Run selected”. If prompted, with a warning message, click “yes” to continue.

### Reports module does not start or stay started

**Symptom:**

* Reports module may start when all modules are started manually but does not start when computer restarts
* The stdout log file will contain this message, `“PacketTooBigException: Packet for query is too large”`

**Resolution:**

a. Open the "my.ini" file under `C:\Program Files\UgandaEMR\MySQL` folder. Note that this file may just appear as “my” without the file extension. Do not modify any other file.  
b. Search for the "max\_allowed\_packet" parameter. If the file does not have it, add the parameter to the file.  
c. To add the parameter, enter the following value in its own line: `max_allowed_packet=5G`

d. Restart the computer.

### Error starting module due to liquibase changeset

**Symptom:** There is an error starting the aijar module with an error as follows:

> Caused by: liquibase.exception.MigrationFailedException: Migration failed for change set liquibase.xml::ugandaemr-01-10-2018-1200::slubwama: Reason: liquibase.exception.DatabaseException: Error executing SQL INSERT INTO patient\_program \(patient\_id, program\_id, date\_enrolled, location\_id, creator, date\_created, voided, uuid\) SELECT patient\_id,\(SELECT program.program\_id FROM program WHERE program.uuid='de5d54ae-c304-11e8-9ad0-529269fb1459'\) AS program,encounter\_datetime AS date\_enrolled,location\_id,encounter.creator,NOW\(\),0,UUID\(\) AS uuid FROM encounter INNER JOIN encounter\_type ON\(encounter\_type.encounter\_type\_id=encounter.encounter\_type\) WHERE encounter\_type.uuid='8d5b27bc-c2cc-11de-8d13-0010c6dffd0f' GROUP BY patient\_id: Cannot add or update a child row: a foreign key constraint fails \(`kamccc`.`patient_program`, CONSTRAINT `patient_in_program` FOREIGN KEY \(`patient_id`\) REFERENCES `patient` \(`patient_id`\) ON UPDATE CASCADE\): Caused By: Error executing SQL INSERT INTO patient\_program \(patient\_id, program\_id, date\_enrolled, location\_id, creator, date\_created, voided, uuid\) SELECT patient\_id,\(SELECT program.program\_id FROM program WHERE program.uuid='de5d54ae-c304-11e8-9ad0-529269fb1459'\) AS program,encounter\_datetime AS date\_enrolled,location\_id,encounter.creator,NOW\(\),0,UUID\(\) AS uuid FROM encounter INNER JOIN encounter\_type ON\(encounter\_type.encounter\_type\_id=encounter.encounter\_type\) WHERE encounter\_type.uuid='8d5b27bc-c2cc-11de-8d13-0010c6dffd0f' GROUP BY patient\_id: Cannot add or update a child row: a foreign key constraint fails \(`kamccc`.`patient_program`, CONSTRAINT `patient_in_program` FOREIGN KEY \(`patient_id`\) REFERENCES `patient` \(`patient_id`\) ON UPDATE CASCADE\): Caused By: Cannot add or update a child row: a foreign key constraint fails \(`kamccc`.`patient_program`, CONSTRAINT `patient_in_program` FOREIGN KEY \(`patient_id`\) REFERENCES `patient` \(`patient_id`\) ON UPDATE CASCADE\) at liquibase.changelog.ChangeSet.execute\(ChangeSet.java:347\) at liquibase.changelog.visitor.UpdateVisitor.visit\(UpdateVisitor.java:27\) at org.openmrs.util.DatabaseUpdater$1OpenmrsUpdateVisitor.visit\(DatabaseUpdater.java:189\) at liquibase.changelog.ChangeLogIterator.run\(ChangeLogIterator.java:58\) at org.openmrs.util.DatabaseUpdater.executeChangelog\(DatabaseUpdater.java:218\) at org.openmrs.module.ModuleFactory.runLiquibase\(ModuleFactory.java:1024\) ... 2 more Caused by: liquibase.exception.DatabaseException: Error executing SQL INSERT INTO patient\_program \(patient\_id, program\_id, date\_enrolled, location\_id, creator, date\_created, voided, uuid\) SELECT patient\_id,\(SELECT program.program\_id FROM program WHERE program.uuid='de5d54ae-c304-11e8-9ad0-529269fb1459'\) AS program,encounter\_datetime AS date\_enrolled,location\_id,encounter.creator,NOW\(\),0,UUID\(\) AS uuid FROM encounter INNER JOIN encounter\_type ON\(encounter\_type.encounter\_type\_id=encounter.encounter\_type\) WHERE encounter\_type.uuid='8d5b27bc-c2cc-11de-8d13-0010c6dffd0f' GROUP BY patient\_id: Cannot add or update a child row: a foreign key constraint fails \(`kamccc`.`patient_program`, CONSTRAINT `patient_in_program` FOREIGN KEY \(`patient_id`\) REFERENCES `patient` \(`patient_id`\) ON UPDATE CASCADE\) at liquibase.executor.jvm.JdbcExecutor.execute\(JdbcExecutor.java:62\) at liquibase.executor.jvm.JdbcExecutor.execute\(JdbcExecutor.java:104\) at liquibase.database.AbstractDatabase.execute\(AbstractDatabase.java:1091\) at liquibase.database.AbstractDatabase.executeStatements\(AbstractDatabase.java:1075\) at liquibase.changelog.ChangeSet.execute\(ChangeSet.java:317\) ... 7 more Caused by: com.mysql.jdbc.exceptions.jdbc4.MySQLIntegrityConstraintViolationException: Cannot add or update a child row: a foreign key constraint fails \(`kamccc`.`patient_program`, CONSTRAINT `patient_in_program` FOREIGN KEY \(`patient_id`\) REFERENCES `patient` \(`patient_id`\) ON UPDATE CASCADE\) at sun.reflect.NativeConstructorAccessorImpl.newInstance0\(Native Method\) at sun.reflect.NativeConstructorAccessorImpl.newInstance\(NativeConstructorAccessorImpl.java:62\) at sun.reflect.DelegatingConstructorAccessorImpl.newInstance\(DelegatingConstructorAccessorImpl.java:45\) at java.lang.reflect.Constructor.newInstance\(Constructor.java:423\) at com.mysql.jdbc.Util.handleNewInstance\(Util.java:411\) at com.mysql.jdbc.Util.getInstance\(Util.java:386\) at com.mysql.jdbc.SQLError.createSQLException\(SQLError.java:1041\) at com.mysql.jdbc.MysqlIO.checkErrorPacket\(MysqlIO.java:4237\) at com.mysql.jdbc.MysqlIO.checkErrorPacket\(MysqlIO.java:4169\) at com.mysql.jdbc.MysqlIO.sendCommand\(MysqlIO.java:2617\) at com.mysql.jdbc.MysqlIO.sqlQueryDirect\(MysqlIO.java:2778\) at com.mysql.jdbc.ConnectionImpl.execSQL\(ConnectionImpl.java:2819\) at com.mysql.jdbc.ConnectionImpl.execSQL\(ConnectionImpl.java:2768\) at com.mysql.jdbc.StatementImpl.execute\(StatementImpl.java:949\) at com.mysql.jdbc.StatementImpl.execute\(StatementImpl.java:795\) at liquibase.executor.jvm.JdbcExecutor$1ExecuteStatementCallback.doInStatement\(JdbcExecutor.java:92\)at liquibase.executor.jvm.JdbcExecutor.execute\(JdbcExecutor.java:55\)

**Resolution:**

Open Heidi or the mysql command line and run the following query:

> ```sql
> SET FOREIGN_KEY_CHECKS = 0;
>
> INSERT INTO patient_program (patient_id, program_id, date_enrolled, location_id, creator, date_created, voided, uuid)
>             SELECT patient_id,(SELECT program.program_id FROM program WHERE program.uuid='de5d54ae-c304-11e8-9ad0-529269fb1459') AS program,encounter_datetime AS date_enrolled,location_id,encounter.creator,NOW(),0,UUID() AS uuid FROM encounter INNER JOIN encounter_type ON(encounter_type.encounter_type_id=encounter.encounter_type) WHERE  encounter_type.uuid='8d5b27bc-c2cc-11de-8d13-0010c6dffd0f' GROUP BY patient_id;
>
> INSERT INTO liquibasechangelog (ID, AUTHOR, FILENAME, DATEEXECUTED, ORDEREXECUTED, EXECTYPE, MD5SUM, DESCRIPTION, COMMENTS, TAG, LIQUIBASE) VALUES ('ugandaemr-01-10-2018-1200', 'slubwama', 'liquibase.xml', '2020-01-24 10:58:37', 10894, 'EXECUTED', '3:2dde7e3cf9f530145011c6b2fda15cc9', 'Custom SQL', 'Move all Patients Ever enrolled in Facility Based Individual Management DSDM', null, '2.0.5');
>
> SET FOREIGN_KEY_CHECKS = 1;
> ```

### The visits page shows a UI Framework Error - No row with the given identifier exists: \[org.openmrs.Form\#32\]

**Symptom:** The UI framework error is shown when displaying a list of visits from the patient dashboard

**Resolution:**

Open Heidi or the mysql command line and run the following query:

> ```sql
> UPDATE encounter SET encounter.form_id = (SELECT form.form_id FROM form WHERE form.uuid = '244da86d-f80e-48fe-aba9-067f241905ee') WHERE encounter.form_id = 32;
> ```

## CHECK LIST

1 Did the backup complete successfully?  
2 On the login page, does the UgandaEMR version show Ver 3.0.0-alpha-recency-x?  
3 Are all the following modules turned on?  
a. UgandaEMRPOC  
b. Aijar  
c. Database Backup Module  
d. UgandaemrSync  
e. Reporting

4 Was the “Dhis2 organisation uuid” for this facility entered in settings?  
5 Was the “Hts recency” value set to “true” in the settings?  
6 Was the “Recency Server URL” entered in settings?  
7 Was the “Recency Server Password” entered in settings?  
8 Was the computer restarted after all configurations were done?  
9 Do you see the recency question in the HTS client card?  
10 Were the report fixing steps outlined in the "Known issues" run?

