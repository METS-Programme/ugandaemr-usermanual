## Patient Flags
These flags are a clinical decision support to highlight important aspects of a patient's treatment 

The flags use the traffic light analogy as follows:
* Green – information for an upcoming e.g., Upcoming appointment, Due for Viral Load
* Orange – warning, prepare to take action e.g., Missed appointment
* Red – take action now e.g., Lost, Lost to Followup, Overdue for Viral Load

### Troubleshooting Tips
#### Module cannot start create patientflags_tag_role 
The error message displayed when starting the module is 
``` 
Error while running sql: CREATE TABLE patientflags_tag_role (
			tag_id int(11) NOT NULL,
			role
			varchar(50) NOT NULL,
			KEY tag_id (tag_id),
			KEY role (role),
			CONSTRAINT
			FOREIGN KEY (tag_id) REFERENCES patientflags_tag (tag_id),
			CONSTRAINT
			FOREIGN KEY (role) REFERENCES role (role)
			) ENGINE=InnoDB DEFAULT
			CHARSET=utf8 . Message: Cannot add foreign key constraint
```

The root cause of this that the character set for the patientflags_tag_role table, utf8, is different from the role table. 

Run the script below to change the characterset of the role and related tables 
```
/*!40101 SET @OLD_CHARACTER_SET_CLIENT = @@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS = @@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION = @@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE = @@TIME_ZONE */;
/*!40103 SET TIME_ZONE = '+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS = @@UNIQUE_CHECKS, UNIQUE_CHECKS = 0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS = @@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS = 0 */;
/*!40101 SET @OLD_SQL_MODE = @@SQL_MODE, SQL_MODE = 'NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES = @@SQL_NOTES, SQL_NOTES = 0 */;

ALTER TABLE `role` CONVERT TO CHARACTER SET utf8;
ALTER TABLE `role_role` CONVERT TO CHARACTER SET utf8; 
ALTER TABLE `role_privilege` CONVERT TO CHARACTER SET utf8;
ALTER TABLE `user_role` CONVERT TO CHARACTER SET utf8;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;
``` 
