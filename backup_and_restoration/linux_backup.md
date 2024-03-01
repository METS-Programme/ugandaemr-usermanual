## LINUX MYSQL DATABASE BACKUP USING AUTOMATIC SCHEDULED JOBS

1. Ensure mysqldump function is available by typing

`mysqldump - -version`

2. If mysqldump is installed, proceed to step 3. If not please install mysqldump using

`sudo apt install mariadb-client`

3. Install Zip

`sudo apt install zip`

4. Next, we are to write a script to backup database using mysqldump 
5. Create a new directory for storing the backups:

`sudo mkdir /var/backups/mysql`

6. Create a new shell script that performs the backup and compression:

`sudo nano /usr/local/bin/mysql-backup.sh`

7. In the text editor, paste the following code:Adjust where necessary

    ```
    # Set the database credentials
    
    DB_USER="openmrs"
    
    DB_PASS="openmrs"
    
    DB_NAME="openmrs"
    
    # Set the backup filename and location
    
    BACKUP_DIR="/var/backups/mysql"
    
    BACKUP_FILE="$BACKUP_DIR/openmrs-backup-$(date +%Y%m%d-%H%M%S).sql"
    
    COMPRESSED_FILE="$BACKUP_DIR/openmrs-backup-$(date +%Y%m%d-%H%M%S).zip"
    
    # Create the backup file ensure to change your mysql.sock if it is different from the default one
    
    mysqldump -u "$DB_USER" -p"$DB_PASS" -d "$DB_NAME" > "$BACKUP_FILE"
    
    # Compress the backup file
    
    zip -r "$COMPRESSED_FILE" "$BACKUP_FILE"
    
    chmod 666 $COMPRESSED_FILE
    
    # Remove the original backup file
    
    rm "$BACKUP_FILE"
   ```
8. Save and close the file (Ctrl+X, Y, Enter).

9. Make the script executable:

`sudo chmod +x /usr/local/bin/mysql-backup.sh`

10. Set up a weekly cron job to run the backup script:

`sudo crontab -e`

11. Add at the end of the file the following line:

`0 16 \* \* \* /usr/local/bin/mysql-backup.sh`

Above example (0 16 \* \* \*) means this job runs every day at 16:00

Change the timing of the cron job to suite you and save.

Done .

## SENDING BACKUPS TO REMOTE SERVER  
In case you want to send backups to a remote server
REQUIREMENTS :
- REMOTE SERVER 
- REMOTE USER 
1. Generate SSH keys on your local server(facility machine) if you haven't already done so:

`ssh-keygen -t rsa`

2. Press Enter to accept the default file location and passphrase or specify your preferred options.

3. Copy the public key to the remote server:

`ssh-copy-id user@remote_host`

4. This will prompt for remote host password  
5. Test the connection using `ssh user@remote_host` to login with out password. If successful, then our local machine is now able to accessible the remote without password

6. Edit the mysql-backup.sh file to add the following code at the end of the file

```
#Variables

REMOTE_USER="remoteuser" # Remote server username

REMOTE_HOST="remote-server IP" # Remote server hostname or IP address

REMOTE_DIR="//path/to/backups/" # Path to remote directory (change as needed)

scp "$COMPRESSED_FILE" "$REMOTE_USER"@"$REMOTE_HOST":"$REMOTE_DIR"

if \[ $? -eq 0 \]; then

echo "File $filename transferred successfully."

else

echo "Error: Failed to transfer file $filename."

fi
```


7. Save the file and test it by running sudo sh /path/to/mysql-backup.sh  
8. File transferred successfully.