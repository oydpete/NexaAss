Outline 
[TASK 1]()

[TASK 2](https://github.com/oydpete/NexaAss/blob/main/TASK%202.md#task-2)

[TASK 3]()
TASK 2.md

# [TASK 1]()

# USER AND ROLES MANAGEMENT

Your company recently hired five new developers who need access to the development server. Your task is to:

1. Create user accounts for them and add them to the developers group.\

2. Ensure they have read and execute permissions for /var/www/project but cannot modify files

3. Restrict SSH access for two of them, who should only log in locally.

# Created a Bash Script to Automate the Whole Processes

***

    #!/usr/bin/bash 

## **SOLUTION 1**

### **1. CREATE USER ACCOUNT FOR THEM AND ADD THEM TO DEVELOPER GROUP.**

### STEP 1

 **- Create  all new Users**

    Sudo useradd JrDev1

    sudo useradd JrDev2

    sudo useradd Dev3

    sudo useradd TeamLead

    sudo useradd TeamLead2 

### STEP 2

 **- Create Developers Group**

    sudo groupadd Developers
 
            

### STEP 3

**- Add All New Users To Developers Group**

    sudo usermod -aG Developers JrDev1

    sudo usermod -aG Developers JrDev2

    sudo usermod -aG Developers Dev3

    sudo usermod -aG Developers TeamLead

    sudo usermod -aG Developers TeamLead2

### STEP 4

**- Print All Users in Developers Group**

    getent group Developers | awk -F: '{print $4}'

### **2. ENSURE THEY HAVE READ AND EXECUTE PERMISSION FOR /var/www/project BUT CANNOT MODIFY FILES**

### STEP 1

 **- Creating The /var/www/project File**

    sudo mkdir -p /var/www/project

### STEP 2

 **- Changing Ownership Of /var/www/project To Developers Group**

    sudo chown -R :Developers /var/www/project

****************

### STEP 3

 **- Give Group Developer Permission to only execute and read /var/www/project but not modifty it**

    sudo chmod 750 /var/www/project

### **3. RESTRICT SSH ACCESS FOR TWO OF THEM, WHO SHOULD LOGIN LOCALLY**

****************

### STEP 1

 **- start ssh service**

        sudo service ssh start

****************

### STEP 2

 **- To confirm if SSH is working**

        sudo service ssh status

*******

### STEP 3

 * Edit the /etc/ssh/sshd_config to deny ssh access to JrDev1 & JrDev2**

        sudo vim /etc/ssh/sshd_config

* Screenshot of Vim Editor is Shown Below

    ![alt text](crt1.png)


****

### STEP 4

* To Restart SSH

        sudo service ssh restart

* Screenshot to Confirm if Users JrDev1 & JrDev2 can ssh

![alt text](<Testing restriction.png>)

## Here is a Screenshot of Bash Script output

![alt text](<Script Output.png>)

# TASK 2

# System Monitoring & Performance Analysis

Your team has reported server slowness during peak hours. Your goal is to:

1. Identify the top resource-consuming processes.

2. Check disk usage, ensuring logs are not consuming excessive space.

3. Monitor real-time system logs for anomalies.

### SOLUTION 2

****

1. **IDENTIFY THE TOP RESOURCES CONSUMING PROCESSES**

### STEP 1

* Show all the Processes

      TOP

*Screenshot of Output is shown Below

![alt text](<top output.png>)

********

### STEP 2

***

* Terminate unncessary processes

        sudo kill -9 <PID>
        
        # Subtitute for  PID of the Processes 

* Screenshot to Confirm Kill
![alt text](<kill confirm.png>)


**Note : Nginx Process has been killed** 

2. **CHECK DISK USAGE , ENSURING LOGS ARE NOT CONSUMING EXCESSIVE SPACE**

****

### STEP 1

* To Check Disk Size

        df -h

# Task 3

# Application Management (Installing and Managing Nginx)

The development team needs an Nginx web server for a new microservice. You need to:

1. Install and enable Nginx

2. Ensure it starts on boot

3. Verify if it is running

4. Restart it when necessary

****

### 1. **INSTALL AND ENABLE NGINX**

### STEP 1 AND 2

* Install Nginx

        sudo apt update
        sudo apt install nginx 

****

* Enable and Ensure Nginx start on boot

        sudo systemctl enable nginx

### STEP 3


******

* Verify if Nginx is running

         sudo systemctl status nginx

### STEP 4

* Restart Nginx if it crashes

        sudo systemctl restart nginx

# Task 4

# Networking and Security

Security is a top priority at HypotheticalCorp. Your task is to:

1. Block all incoming traffic except SSH (22) and HTTP (80).

2. Check which ports are currently open.

3. Set up SSH key-based authentication.

******

#h2
### Enable ufw 
        
        sudo ufw enable

*********


### 1. **BLOCK ALL INCOMING TRAFFIC EXCEPT SSH (22) AND HTTP (80)**

********


### STEP 1 

* Block all incoming Traffic 

        sudo ufw default deny incoming

*******



### STEP 2

* Allow incoming for ssh (22) and http (80)

        sudo ufw allow 80/tcp
        sudo ufw allow 22/tcp

*******


### STEP 3

* Allow for all outgoing traffic

        sudo ufw allow outgoing

*********

### 2. CHECK WHICH PORTS ARE CURRENTLY OPEN

    sudo ufw status verbose

* Screenshot of the process is attached here 

![alt text](<XIII Q4 Secure PORT Access.png>)


**********

### 3. SET UP SSH KEY-BASED AUTHENTICATION

*********

### STEP 1

* Open /etc/ssh/ssh/ssh_config in vim Editor

            sudo vim /etc/ssh/ssh/ssh_config 

* Screenshot is shown Here

![**alt text**](<XV Q4 SSH EDIT PAGE.png>)
