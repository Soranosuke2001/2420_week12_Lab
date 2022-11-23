# ACIT 2420 Lab 12

## Table of Contents

- [Requirements Before Starting](#requirements-before-starting)
- [Installing NGINX](#installing-nginx)

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




