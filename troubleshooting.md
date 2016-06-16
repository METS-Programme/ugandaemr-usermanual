# Common Troubleshooting Tips
This section contains fixes for common errors that occur when using UgandaEMR
## I have created a visit but the encounter has different dates
Delete the encounter then delete the visit and re-enter the encounter 
## Location does not support visits
This error occurs when the user session has expired therefore there is no location selected in the top right hand corners. 

Log out of your account then log back in 
## OpenMRS Cannot Start - Error Occured at Startup 
At starting up the screen looks like the image below 

![OpenMRS Startup Error](images/openmrs_startup_error.jpeg)

The most common cause of this is due to a corruption of the lucene search indexes which is solved by deleting the lucene folder and restarting

1. Go to C:/Application Data/OpenMRS folder 
2. Delete the lucene folder 
3. Restart your computer - this has the effect of restarting all services 
