# Standard Operating Procedure for Setup of a Virtual Linux Server for Web Application Tests
### Pinegins Org. | 123 Henlow Bay, Winnipeg, MB | 123-456-7890

#### Purpose
The purpose of this socument is to describe Pinegins' standard procedure for creating a virtual Linux Server dedicated to Web Application Testing. This standard ensures proper installation, correct configuration and adherence to company policies to promote consistency and organization across Pinegins' infrastructure. 

#### Audience
This document is intended for network administrators, server administrators and any other members of the Information Technology (IT) department involved in the creation, deployment and testing of physical and virtual servers. This document may also be intended for Network Architects and Virtual Deployment Administrators. 

#### Approval Table
Version | Date      | Name        | Role
--------|-----------|-------------|-----
1.0     |2025-11-19 |Daria Pinegin|Author

#### Scope
This document describes the guidelines and procedures for creating a virtual Linux server designated for web application testing. This includes:
1. The pre-deployment planning and the infrastructure assessment.
2. The creation of the virtual server and Operating System (OS) installation.
3. The post-installation configuration.
4. The installation and configuration of the necessary services and tools.
5. Troubleshooting and documentation guides. 

#### Definitions
SecOps - Security Operations.
OS - Operating System. 
VMWare Workstation - The hypervisor client Pinegins uses for all virtual servers. 
Ubuntu Desktop/Ubuntu Server - The Linux Distribution that is used for all virtual Linux-based Operating System settings in Pinegins Org. 

#### Accountabilty Matrix
Task/Steps                             | Delegate                         | Emergency Contact   | Non-Emergency Contact | Reviwed/Approved
---------------------------------------|----------------------------------|---------------------|-----------------------|-----------------
Pre-deployment planning and assessment | Network Administrator            | Phone: 431-333-3333 | smcbride@pinegins.org | IT Manager
Configuration of Virtual Machines      | Virtual Deployment Administrator | Phone: 431-444-4444 | hgutcher@pinegins.org | IT Manager
Installation of a Linux OS             | Server Administrator             | Phone: 431-555-5555 | bgenik@pinegins.org   | IT Manager
Post-Installation Verfication          | Quality Assurance Agent          | Phone: 431-666-6666 | dpinegin@pinegins.org | QA Manager
Post-Installation Configuration        | Server Administrator             | Phone: 431-555-5555 | bgenik@pinegins.org   | SecOps Manager
Installation of Services               | Server Administrator             | Phone: 431-555-5555 | bgenik@pinegins.org   | SecOps Manager
Post-Services Verification             | Quality Assurance Agent          | Phone: 431-666-6666 | dpinegin@pinegins.org | QA Manager
Documentation of Server                | Documentation Team               | Phone: 431-777-7777 | fliang@pinegins.org   | Author

#### Execution Steps  
##### Step 1: Pre-Deployment Planning and Infrastructure Assessment  
__Step 1.1: Identify the Requirements__
- Under the leadership and approval of the SecOps Manager, determine the exact specifications of the server that the Software Development team will require. This may include:
  - The specific required services needed for web application testing.
  - The amount of web application testing that will happen conqurently.
  - The amount of users that will be logged in simultaneously.
  - The way that the server should be made available to be authenticated to.
  - Any other additional requirements or requests. 
- Define and needed hardware resources needed for deployment, such as the number of needed processor cores, memory, disk space, network cards and power supplies. This may also include redundant power sources.  

__Step 1.2: Plan the Resource Allocation__
- Under the approval of the IT Manager, check and ensure that the current physical servers can accomodate the hardware requirements defined above. Account for the time that the server needs to be available for and the amount of conqurent users.
- If not defined above, estimate the amount of processors, memory and disk space needed to store the appropriate files needed for the developers. In addition, estimate the amount of memory and disk space needed for the requested services and applications.
- Estimate the disk space needed for the estimated size and number of databases. 
- Discuss the way of the network access with the SecOps Team and ensure any other hardware or software resources needed are accounted for and are available.  

__Step 1.3: Confirm and Consult with Management__
- Present the deployment proposal to the Software Development Management to receive any additional requirements.
- Present the revised proposal to upper management, including the SecOps Team, to receive an approval.  
##### Step 2: Creation of the Virtual Server
__Step 2.1: Access the Hypervisor Client__  
- Launch the VMWare Workstation Client from a computer with sufficient privileges.
- Create a new Virtual Machine:
    1. On the top left corner, select __File__ and then __New Virtual Machine__.  
    2. Select the Virtual Machine Configuration Type (Typical or Custom).
    3. On the __Guest Operating System Installation__ page, select __I will Install Operating System Later__.
    4. On the __Select a Guest Operating System__ page, select __Linux__ and choose the appropriate Ubuntu version from the dropdown menu.
    5. On the __Name the Virtual Machine__ page, give the virtual machine a name, adhering to the Pinegins' Asset Classification and Naming Policy.
    6.  On the __Specify Disk Capacity__ page, specify the disk capacity, __in GB__, allocated to the virtual machine. In addition, specify wheter the disk should be a single file or should be split into multiple files. 
    7.  On the __Ready to Create Virtual Machine__ page, verfiy the setting. After the verification, click __Finish__.
- Verify the creation of the virtual machine, as well as the necessary hardware resources. If the hardware resources need to be changed:
    1. Select __VM__ from the top bar, and click on __Tools__.
    2. To add an additional component, click on __Add__, select the component and click __Finish__.
    3. To remove a component, click the component from the left pane and select __Remove__.
    4. To change the amount allocated of a component, select the component and change the amounts shown in the right pane.
    5. Once done, click __OK__ to save changes and exit.
##### Step 3: Operating System Installation
__Step 3.1: Attach the Installation Media to the Virtual Machine__
- Ensure that the latest version of the Ubuntu has been downloaded in the form of an ISO file. If there is no ISO file, do the following to download it:
    1. Naviage to the official Ubuntu website. This can be done through a web browser with the search query of "*distribution name* LTS download".
    2. On the web page, scroll to the section with the latest stable version and __Long Term Support (LTS)__. Click __Download__.
    3. If prompted, select the processor architecture for the ISO file (ensure it is the same architecture as the processors used in the physical hardware of the virtual server).
    4. Wait until the download finishes.
- Navigate to the VMWare Workstation Client and attach the installation media:
    1. Click on the virtual machine that has been previously created. Select __Edit virual machine settings__.
    2. In the left pane, select __CD/DVD (SATA)__.
    3. Ensure that __Use ISO image file__ is selected.
    4. Click on the __Browse...__ button and navigate to the directory where the ISO file has been downloaded. Select the file. 
    5. Once the file has been selected and the path to the ISO is specified in the ISO image file field, click __OK__ to save changes and exit.  

__Step 3.2: Install the Linux Operating System__
- Navigate through the installation prompts in the virtual machine. Remember to specify the following settings:

Setting                              | Value
-------------------------------------|----------------------------------------------------------------------------------------
Hostname                             | A name adhering to the Pinegins Naming Convention Document. 
Administrative username and password | A username and password adhering to the Pinegins Creation of Administrative Users and Passwords Guideline. 
Timezone                             | America/Winnipeg
- Ensure that there are no errors during the installation. If there are, troubleshoot further. 

##### Step 4: Post-Installation Verification
__Step 4.1: Verify System Functionaltiy__
- With the leadership of the Quality Assurance Team and the management of the IT Manager, ensure that Ubuntu has been successfully installed and there have been no errors.
- Ensure that the virtual server has all the necessary hardware requirements as initally requested.
- Verify that the hostname is set correctly using the following command:
    ```
    hostnamectl
    ```

##### Step 5: Post-Installation Configuration
__Step 5.1: Verify and Connect the Server to the Network__
- Ensure to set the following settings on the machine to give it network access:

Setting                              | Value
-------------------------------------|------
Static IP address                    | An allocated address from the 192.168.32.0/26 range. 
Default Gateway                      | The default gateway for the 192.168.32.0/26 range. 
DNS Servers                          | The on-premises DNS server for the 192.168.32.0/26 range. 

- Verify that the virtual server has network and Internet access. In addition, ensure that it can be accessed by members of the Software Development department.
- Verify that that the timezone settings are correct using the following command:
    ```
    timedatectl
    ```
- Update the system using the following commands:

    ```
    sudo apt update
    sudo apt upgrade
    ```

##### Step 6: Installation of Services
__Step 6.1: Install the Necessary Services for Hosting Web-Applications__
- To install the necessary services, ensure that the previous steps have been successfully completed and that the virtual machine passed all the previous checks.
- Install and Configure Apache Web Server:
    1. Install Apache Web Server
    ```
    sudo apt install apache2
    ```
    2. List the firewall application profiles:
    ```
    sudo ufw app list
    ```
    3. Use the most restrictive profile that only opens port 80:
    ```
    sudo ufw allow 'Apache'
    ```
    4. Verify the change by listing the firewall rules and noting the ones that allow HTTP traffic:
    ```
    sudo ufw status
    ```
- Install MySQL server and start the service:
    1. Install MySQL Server
    ```
    sudo apt install mysql-server
    ```
    2. Ensure that the MySQL service is running:
    ```
    sudo systemctl status mysql.service
    ```
    3. If the service is not running, start it:
    ```
    sudo systemctl start mysql.service
    ```
- Install and set-up PhP:
    1. Install PhP:
    ```
    sudo apt install php8.4
    ```
    2. Verify the install by retrieving the version number:
    ```
    php -v
    ```
    3. Install the common modules and extensions that are used with PhP:
    ```
    sudo apt install php-cli php-fpm php-json php-common php-mysql php-zip php-gd php-mbstring php-curl php-xml php-pear php-bcmath
    ```
    4. List all the loaded PhP modules:
    ```
    php -m
    ```
__Step 6.2: Install the Necessary Services for Programming__
- Verify that Python is installed (it should be pre-installed with the installation of Ubuntu):
  ```
  python3 --version
  ```
- Install OpenJDK on Ubuntu:
    1. Install the Java Runtime Environment:
    ```
    sudo apt install default-jre
    ```
    2. Install the Java Development Kit:
    ```
    sudo apt install default-jdk
    ```
    3. Verify the install by retrieving the version number:
    ```
    java -version
    ```
- Install nodejs:
    1. Use the following command to install nodejs:
    ```
    sudo apt install nodejs
    ```
    2. Verify the install by retrieving the version number:
    ```
    node -v
    ```
    3. If the node.js package manager is also needed, install it as well:
    ```
    sudo apt install npm
    ```
##### Step 7: Post-Services Verification
__Step 7.1: Verify Full-System Functionality and Security__
- With the leadership of the Quality Assurance Team and the management of the IT Manager, ensure that the web server is functional.
- Confirm that the neeeded services and applications operate properly.
- Verify that the virtual server has network and Internet access. In addition, ensure that it can be accessed by members of the Software Development department.
- Validate that the web server and the installed web services are compliant with Pinegins' security policies and guidelines.

### Step 8: Documentation of the Server
__Step 8.1: Document the Virtual Server Configurations__
- Record the hostname of the server, domain name, IP address and all other network information.
- Record the Operating System version and the allocated hardware resources. 
- Record all the firewall configurations that were performed as well.
- Record all performed configurations on the server, including the installed services and their configurations.
- Ensure that all critical data, such as passwords and usernames, are also recorded.
- Update the documentation with the new server information from above.

__Step 8.2: Documentation Transfer__
- Seperate the documentation and provide each section to the relevant departments. The documentation should include the access and management information.
- Provide the Software Development department with instructions on how to access the server and how to use it. 
- Ensure a full copy of the documentation is kept. 
 

#### Reference and Related Documents
- [How to Install Apache Web Server on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-20-04)  
- [How to install MySQL on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04)  
- [How to Install PHP on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-php-8-1-and-set-up-a-local-development-environment-on-ubuntu-22-04)  
- [How to Install Node.JS on Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04)  
#### Revision History
Version | Date     | Name and Contact Information        | Changes Made
--------|----------|-------------------------------------|-------------
1.0     | 19/11/25 | Daria Pinegin/dpinegin@pinegins.org | Initial Publication of the Documentation
