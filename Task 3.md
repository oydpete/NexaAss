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
