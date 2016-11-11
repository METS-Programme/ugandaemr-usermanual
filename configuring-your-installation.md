## UgandaEMR Configuration 
### Tomcat Configurations

1. Go to Windows Startup Menu
2. Search for Configure Tomcat and click on it
3. On the Configuration Select Java Tab
4. Delete values in the Initial memory pool and Maximum memory pool
5. Click okay
6. Restart Tomcat

### MySQL 
1. Open the file my.cnf in C:\Program Files\MySQL Server\MySQL Server 5.5
2. In the section that starts with [mysqld] add the line `innodb_buffer_pool_size=2G`
3. Restart the computer 



