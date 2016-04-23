# Installation
## Pre-requisites
### Minimum Computer Requirements

1. Windows 7 (both 32-bit and 64-bit versions supported)
2. 4GB of RAM
3. 1.5GHz duo core processor

### Minimum Software Requirements
1. Java 7
2. Tomcat 7
3. MySQL 5.5
4. Mozilla Firefox 44

## Manual Installation
### Requirments for Manal Installation
This process will be added at a later stage, as currently the automatic installation is the easiest way to get the required configuration

## New Installation - Using the installer
The installer provides all the pre-requisite components for setting up UgandaEMR, parts of this guide have been adopted from the World Health Organization (WHO) OpenMRS Express guide.

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

2. Agreement of installation
![](images/installer/1.2-agreement.jpg)
3. Selecting components to install.
![](images/installer/1.3-components.jpg)
4. Determining Installation directory.
![](images/installer/1.4-location.jpg)
5. Determine Shortcut directory
![](images/installer/1.5-shortcut.jpg)

**Required Software**

6. Install Java
![](images/installer/2.1-inst-java.jpg)

![](images/installer/2.3-java.jpg)

![](images/installer/2.4-java-2.jpg)

![](2.5-inst-java-complete.jpg)

7. Install Mysql
![](images/installer/3.1-mysql-configure.jpg)

![](images/installer/images/installer/3.2-standard.jpg)

![](images/installer/3.3-comd1.jpg)

![](images/installer/3.4-password-for-root.jpg)

![](images/installer/3.5-execute.jpg)


![](images/installer/3.6-mysql-finished.jpg)

8. Install Tomcat.
![](images/installer/4.1-tomcat-installation.jpg)

![](images/installer/4.2-tomcat-agree.jpg)


![](images/installer/4.3-java-directory.jpg)

![](images/installer/4.4-tomcat-componets.jpg)

![](images/installer/4.5-configure-tomccat.jpg)

![](images/installer/4.6-tomcat-location.jpg)
9. Install Firefox

![](images/installer/5.1-fire.jpg)



![](images/installer/5.3-fire-fox-inst.jpg)


![](images/installer/5.4-fire-standard.jpg)


![](images/installer/5.5-fire-fox-directory.jpg)



![](images/installer/5.2-fire-fox-start.jpg)
**Completion **

10. Complete Installation

![](images/installer/6.0-complete-installation.jpg)

### Post-installation Configuration

11. Start Application.


This installation guide is pictorial.

Step 1 Check the Computer Operating System Bit

Step 2 Launch the installer either 32 bit or 64 bit, depending on the computer bit.

Step 3 Agree to the terms and conditions in the installer

Step 4 Select components to install

Step 5 Select default directory in which openmrs will install. NB. Leave the current/default preselected option.
