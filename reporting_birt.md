## BIRT Reporting Module 
The BIRT module provides a number of pre-built reports that are used to provide facility level metrics as well as MoH HMIS reports

**Before starting to use birt reporting make sure that the birt module is running**

To check that module is running
1. Select legacy ui on home
![Select EID legacy ui from home](images/home_select_legacy.png)
2. You will see the birt reporting section on the administration page
![Highlight the birt section on the admin legacy ui ](images/legacy_admin_page_birt_reports.png)
If the Birt reporting does not appear on the administration page, it means that the birt module is not started
If the module is not started, try to start it
![Highlight the birt not started on admin module management ](images/legacy_admin_manage_modules.png)
![Highlight the birt not started on admin module management ](images/module_management_birt_not stated.png)
![Highlight the birt not started on admin module management ](images/module_management_start_birt.png)

If the module is not administration module's page, that means the module is not installed, please refer to birt module installation instructions section

If the module fails to start refer to configuration section

![Highlight the birt not started on admin module management ](images/module_management_birt_start_error.png)
Click on the error detail to see the details of the error
![Highlight the birt not started on admin module management ](images/module_management_birt_error_detail.png)
![Highlight the birt not started on admin module management ](images/module_management_birt_start_error_detail.png)

### Installation
**What you will need**
* Birt module version 2.3.2.1
* Birt report engine vs 2.3_2 (birt.home)
* You also need to create the following directories (will be used in the birt configuration)
  * Directory the will hold data sets (birt.datasetDir)
  * Directory where birt logs will dumped (birt.loggingDir)
  * Directory where generated output will be stored (birt.outputDir)
  * Directory where report designs will be stored (birt.reportDir)

Then
1. Go to manage modules on the legacy administration ui and then add or update module
![Highlight the birt not started on admin module management ](images/legacy_admin_add_module.png)
2. Click choose and then browse where the birt omod file is located
3. Click upload, this will upload and try to start the birt module which will fail. Refer to the configuration section to configure birt
![Highlight the birt not started on admin module management ](images/choose_and_uplaod_birt_module.png)
Error page
![Highlight the birt not started on admin module management ](images/module_management_birt_start_error.png)

### Configurations
To configure birt,
1. Go to legacy ui administration page, then click on advanced settings
![Highlight the birt not started on admin module management ](images/legacy_admin_advanced_settings.png)
2. Look for birt related configurations and change them accordingly (based on the directories you created above)
![Highlight the birt not started on admin module management ](images/birt_configuration.png)
3. After configuring birt accordingly, start birt again

**To add run or edit reports make go to home and then click generate birt reports**

If you get this page, means that birt is not running refer to the above on making sure that birt reports run
![Highlight the birt not started on admin module management ](images/birt_reports_404.png)

### Adding reports

### Editing reports

### Deleting reports

### Running reports

### Troubleshooting