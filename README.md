# ACIT 2420 Lab 12

## Table of Contents

- [Requirements Before Starting](#requirements-before-starting)
- [Installing NGINX](#installing-nginx)
- [Create an HTML File to Serve](#create-an-html-file-to-serve)
- [Writing an NGINX Server Block](#writing-an-nginx-server-block)

- **Note Before Starting:** We will be creating the files using WSL then transfering the files to "web-one". Where the files are created does not matter currently, but when transfering the files, this will matter.

## Requirements Before Starting

- Note: Before beginning this lab, you must create a new server with the hostname set to "web-one" on DigitalOcean.

1. Create a new SSH key.

2. Create a new droplet on DigitalOcean with the hostname set to "web-one".

3. Create a new user on "web-one".

4. Disable login as the root user.

## Installing NGINX

1. Check if there are any updates to be made on your system by using the commmand below.

	`sudo apt update`

	`sudo apt upgrade`

2. To install NGINX, use the command below.

	`sudo apt install nginx`

3. When prompted, "Do You Want To Continue?" Type in "Y" and hit the `Enter` key.

- Note: The download should begin and a progress bar should appear at the bottom of the terminal like the screen shot below.

![NGINX download progress](images/ss1.png)

4. When the screen with the image below pops up, press `Tab` on your keyboard then press `Enter`

![Package Configuration Restart Prompt](images/ss2.png)

You have now successfully installed NGINX

## Create an HTML File to Serve

1. Create a "index.html" file by using the command below.

	`touch index.html`

2. Add the following contents inside the HTML file using the `vim` tool.

	```
	<!DOCTYPE html>
	<html lang="en">
	<html>
    		<head>
			<meta charset="UTF-8" />
        		<title>Example Site for 2420</title>
    		</head>
    		<body>
        		<h1>Success!</h1>
        		<h2 style="color: red;">All your internets are belong to us!</h2>
    		</body>
	</html>
	```

You have now successfully created the index.html document

## Writing an NGINX Server Block

1. Create a file with the file name set as the IP address for your DigitalOcean server.

	`touch 137.184.7.84`

2. Add the following contents to the file created in step 1 by using the `vim` tool.

	```
	server {
        	listen 80;
        	listen [::]:80;

        	root /var/www/137.184.7.84/html;
        	index index.html;

        	server_name 137.184.7.84;

        	location / {
                	try_files $uri $uri/ =404;
        	}
	}	
	```

- Note: The IP address shown above will be different. Use the IP address for web-one created on DigitalOcean.

You have successfully created the server block for NGINX




