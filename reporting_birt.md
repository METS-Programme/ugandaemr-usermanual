## BIRT Reporting Module 
The BIRT module provides a number of pre-built reports that are used to provide facility level metrics as well as MoH HMIS reports

**Before starting to use birt reporting make sure that the birt module is running**

To check that module is running
1. Select legacy ui on home
![Select legacy ui from home](images/home_select_legacy.png)
2. You will see the birt reporting section on the administration page
![Highlight the birt section on the admin legacy ui ](images/legacy_admin_page_birt_reports.png)
If the Birt reporting does not appear on the administration page, it means that the birt module is not started
If the module is not started, try to start it
![Birt legacy admin manage modules](images/legacy_admin_manage_modules.png)
![Birt module not started](images/module_management_birt_not stated.png)
![Birt module start birt](images/module_management_start_birt.png)

If the module is not administration module's page, that means the module is not installed, please refer to birt module installation instructions section

If the module fails to start refer to configuration section

![Birt module start error page](images/module_management_birt_start_error.png)
Click on the error detail to see the details of the error
![Birt module show detailed error select](images/module_management_birt_error_detail.png)
![Birt module show detailed error](images/module_management_birt_start_error_detail.png)

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
![Admin page add module](images/legacy_admin_add_module.png)
2. Click choose and then browse where the birt omod file is located
3. Click upload, this will upload and try to start the birt module which will fail. Refer to the configuration section to configure birt
![Admin choose and upload birt module](images/choose_and_uplaod_birt_module.png)
Error page
![Birt 404 page](images/module_management_birt_start_error.png)

### Configurations
To configure birt,
1. Go to legacy ui administration page, then click on advanced settings
![Admin page advanced settings](images/legacy_admin_advanced_settings.png)
2. Look for birt related configurations and change them accordingly (based on the directories you created above)
![Birt configuration page](images/birt_configuration.png)
3. After configuring birt accordingly, start birt again

**To add run or edit reports make go to home and then click generate birt reports**
![Birt reports home page](images/birt_reports_home.png)
If you get this page, means that birt is not running refer to the above on making sure that birt reports run
![birt 404](images/birt_reports_404.png)

### Adding reports
1. Click add new report in the main birt reports main page
![Birt add](images/birt_add.png)
2. The form for entering new report appears which you then fill and click save. This brings another page for adding the report design
![Birt new form](images/birt_new_form.png)
![Birt upload report](images/birt_add_upload_report_design.png)
![Birt select report design](images/birt_add_select_report_design.png)
![Birt save report](images/birt_report_save.png)
![Birt add saved report](images/birt_add_saved.png)
![Birt home](images/birt_reports_home.png)

### Editing and deleting reports
1. To edit or delete a report go to birt home and click the edit button, This create report, but which allows you to edit or delete
![Birt reports home choose edit](images/birt_reports_home_edit.png)

### Running reports
1. To run reports you click the run button
![Birt reports home choose run](images/birt_reports_home_run.png)
2. This take you a page where you can input any parameters if required
![Birt reports example run page](images/birt_run_report_page.png)
3. You can also choose how you want the report to be rendered
![Birt reports choose download format before run](images/birt_run_report_choose_formart.png)
4. You then click generate to run, display,download the report
