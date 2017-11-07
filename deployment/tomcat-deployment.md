AWS EC2
====

Launching and configuring EC2 instances is covered in more depth in the AWS section of dev_fundamentals. That said, here is a quick breakdown.

Launching EC2 Instance
----

* Log into your AWS account (http://aws.amazon.com)
* Navigate to the EC2 section
* Be sure you're in the proper availability zone
* Click "Launch Instance"
* Choose Amazon Linux and proceed through the setup
* Use an existing .pem security file or choose to create (and download) a new .pem file (save this to your ~/.ssh dir on your local machine)
* Be sure that the only open ports are port 22 (limited to just your IP) and port 8080 (open to the world)
** Anytime your IP changes you'll need to update the security group in EC2 if you wish to connect to this server
* Once the server is running, select the box to the left of the running instance from the "Instances" tab of EC2 console
* Click "Connect" near the top of the screen and follow the instructions to SSH into your new server

SSH and SCP
----
* The SSH command to connect to your server from your CLI will be similar to:
> * `ssh -i ~/.ssh/mexico_1.pem ec2-user@ec2-52-10-203-209.us-west-2.compute.amazonaws.com`
* The SCP command to copy your .war file to your server will be similar to:
> * `scp -i ~/.ssh/mexico_1.pem target/application.war ec2-user@ec2-52-10-203-209.us-west-2.compute.amazonaws.com:~`

TO BE CONTINUED`


Tomcat Deployment
====

Apache Tomcat is used to deploy your Java Servlets and JSPs. So in your Java project you can build your WAR (short for 
Web ARchive) file, and just drop it in the webapps directory in Tomcat. So basically Apache is an HTTP Server, serving HTTP. 
Tomcat is a Servlet and JSP Server serving Java technologies.

You'll want to be sure the Java version on your server mantches the Java version you compile your application with.

Installing
----

http://tomcat.apache.org/

Tomcat 8
> * `sudo yum install tomcat8-webapps tomcat8-admin-webapps`


Tomcat 9
> * `sudo yum install tomcat9-webapps tomcat8-admin-webapps`

Start
> * `sudo service start tomcat<version> start`

Stop
> * `sudo service start tomcat<version> stop`


Adding admin users to manage apps via {host}:8080/manager/html
> * vim <tomcat_dir>/conf/tomcat-users.xml
> * add the following to the bottom of the file just above the </tomcat-users> tag:
`<role rolename="manager-gui"/>
   <user username="admin" password="admin" roles="manager-gui"/>`


Deploying your applications
----

You have two options:
> * Deploy your apps using the GUI (Manager App) {host}:8080/manager/html

or

> * Copy your war file into the "webapps" folder of the tomcat installation. After copying your .war file into the 
webapps directory your .war will be unpacked and deployed automatically


