# Backup and Restoration 
## Database Backup
UgandaEMR includes a backup module that can be run from the administration interface. 

The Backups are stored in the OpenMRS configuration directory
The two common paths to find the backups are
1. C:\Users\{UserAccount}\Application Data\OpenMRS\backup
2. C:\Application Data\OpenMRS\backup

The steps in the backup are.
1. On the Dash Board Click on the Backup Database icon.
![Dash Board backup button](images/backup/backup1.0.jpg)
2. Click on the Execute database backup now
![](images/backup/backup2.jpg)
3. The backup begins and the progress is shown until completion.
![Backup in progress](images/backup/backup3.jpg)
4. Once the backup is complete, a message is displayed with the status.
![Backup complete](images/backup/backup4.jpg)
## Database Restore 
The UgandaEMR installer includes HeidiSQL a tool that allows the restoration of backup files into the backend database. 