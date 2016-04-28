# Setup and Configuration
## Prerequisites
### Minimum Computer Requirements

1. Windows 7 (both 32-bit and 64-bit versions supported)
2. 4GB of RAM
3. 1.5GHz duo core processor

### Recommended Minimum Software Requirements
1. Java 7 (do not use Java 8)
2. Tomcat 7
3. MySQL 5.5
4. Mozilla Firefox 44

## Manual Setup 
### Requirements for Manual Installation
This process will be added at a later stage, as currently the automatic installation is the easiest way to get the required configuration

## Interactive Setup via installer
The installer provides all the prerequisite components for setting up UgandaEMR, parts of this guide have been adopted from the World Health Organization (WHO) OpenMRS Express guide.

There are separate installation files for 32-bit and 64-bit Windows systems so pick the installation package.

### Installation Directories and Menu Items
The installer creates the following directory structure:

* **Main Directory** - C:\Program Files\UgandaEMR
* **Tomcat Directory** - C:\Program Files\UgandaEMR\UgandaEMRTomcat
* **Mysql Directory** - C:\Program Files\MySQL\MySQL Server 5.5 *TODO: Correct this*
* **OpenMRS Configuration Files** - C:\ApplicationData\OpenMRS *TODO: Correct this*

The following items are also added to the Windows Start Menu:
* **TODO: Add Start Menu Items**

A shortcut link to the UgandaEMR instance is also added to the Desktop **TODO: Add screenshot of desktop with the Shortcut link**

### Installation Overview
![Installation proces overview](images/installer/installation_process.png)

### Installation Steps
1. Launch of the splash screen
![Splash Screen](images/installer/splash.jpg)  

2. License Agreement
![License Agreement](images/installer/1.2-agreement.jpg)  

3. Selecting components to install
![Selecting installation components](images/installer/1.3-components.jpg)

4. Determining Installation directory
![Determining installation directory](images/installer/1.4-location.jpg)
5. Confirm start menu item
![Start Menu Item](images/installer/1.5-shortcut.jpg)

6. Install Java Runtime
![Java configuration](images/installer/2.1-inst-java.jpg)
![Java installation](images/installer/2.3-java.jpg)
![Java installation file copying](images/installer/2.4-java-2.jpg)
![Java installation completion](images/installer/2.5-inst-java-complete.jpg)

7. Install MySQL  
![Server Configuration Wizard](images/installer/3.1-mysql-configure.jpg)  
![Standard Configuration](images/installer/3.2-standard.jpg)
![Windows Service and PATH Configuration](images/installer/3.3-comd1.jpg)
![Security Configuration](images/installer/3.4-password-for-root.jpg)
![Instance configuration](images/installer/3.5-execute.jpg)
![Setup completion status message](images/installer/3.6-mysql-finished.jpg)

8. Install Tomcat  
![Tomcat Setup Wizard Splash page](images/installer/4.1-tomcat-installation.jpg)
![License Acceptance](images/installer/4.2-tomcat-agree.jpg)

![Java Virtual Machine selection](images/installer/4.3-java-directory.jpg) 

![Tomcat Component selection](images/installer/4.4-tomcat-componets.jpg)
![Tomcat Configuration](images/installer/4.5-configure-tomccat.jpg)
![Tomcat directory location](images/installer/4.6-tomcat-location.jpg)

9. Install Firefox
![Firefox Splash screen](images/installer/5.3-fire-fox-inst.jpg)
![Firefox Setup Type](images/installer/5.4-fire-standard.jpg)
![Firefox install location](images/installer/5.5-fire-fox-directory.jpg)
![Firefox install completed](images/installer/5.2-fire-fox-start.jpg)

 10. UgandaEMR Installation completed
![Installation completed splash screen](images/installer/6.0-complete-installation.jpg)

### Post-installation Configuration
**TODO: Work on this section**