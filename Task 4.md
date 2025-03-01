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

![alt text](<../Screenshot/XIII Q4 Secure PORT Access.png>)


**********

### 3. SET UP SSH KEY-BASED AUTHENTICATION

*********

### STEP 1

* Open /etc/ssh/ssh/ssh_config in vim Editor

            sudo vim /etc/ssh/ssh/ssh_config 

* Screenshot is shown Here

![**alt text**](<../Screenshot/XV Q4 SSH EDIT PAGE.png>)
