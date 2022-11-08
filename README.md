# Deploying Stan - Lee web app using Amazon Web Services (AWS) EC2 Instance 

Link of the web app http://ec2-34-224-102-147.compute-1.amazonaws.com/

Deploying an existing web application from one of my previous github repository's "Website-Stan-Lee" using AWS EC2 Instance.

<h3> Steps Undertaken to deploy the web application </h3>

1) Login to AWS account
2) Search for EC2 on the search box.
3) Click on Launch instance on EC2 Dashboard.
- Create an instance name ( Stan-Lee )
- Choose an Amazon Machine Image [Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type]
- Choose Architecture [64-bit (x86)]
- Choose an Instance type (t2.micro)
- Create a keypair
- Launch the instance

<img width="919" alt="aws" src="https://user-images.githubusercontent.com/99300527/200442805-06233027-6c48-4d9b-aab1-e5ef40382ace.PNG">


4) To deploy the web on AWS in this scenario, EC2 instance connect method is used.
5) Select EC2 - Connect option and press connect to open a Linux command shell.
6) Update the system using "sudo yum update" or enable super user commands by typing "sudo su -" in the command line and try updating using "yum update -y"
7) Install the web server httpd by typing the command "yum install -y httpd"
8) Check the status of httpd, which would let us know whether its active or not by typing the command "systemctl status httpd". Since httpd has not been started, it would show as inactive.
9) Next, create a new directory using mkdir command followed by the file name "mkdir temp".
10) Install git in AWS using "sudo yum install git -y"
11) After installation is complete, clone it using the command "git clone https://github.com/Shantanugupta43/Website-Stan-Lee.git ".
12) To look inside the directory, "ls -lrt" command is used. A Website-Stan-Lee directory is created. Enter "cd Website-Stan-Lee" command to move within the directory.
13) In order to make the files work and connect the web server, all the files are moved to /var/www/html using this command "mv * /var/www/html".
14) Set up security groups to control inbound and outbound traffic by going through Instances menu and security section.
15) Add and Edit inbound rules to the following settings.

<img width="695" alt="inbound" src="https://user-images.githubusercontent.com/99300527/200442853-70e79576-71db-409a-b986-74f263ec0731.PNG">

16) Enable httpd through the command "systemctl enable httpd"
17) Start httpd through the command "systemctl start httpd" 
18) Copy the Public IP address and paste on another browser to view the results.
