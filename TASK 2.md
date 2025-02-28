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
![alt text](<../Screenshot/kill confirm.png>)


**Note : Nginx Process has been killed** 

2. **CHECK DISK USAGE , ENSURING LOGS ARE NOT CONSUMING EXCESSIVE SPACE**

****

### STEP 1

* To Check Disk Size

        df -h
