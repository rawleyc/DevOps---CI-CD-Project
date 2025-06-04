<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Rawley Chirume  
**Email:** chirumerawley@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In today's project we will setup a web app in the cloud.

### Key tools and concepts

Services I used were, SSH and VS Code. Key concepts I learnt was how to edit files and explore directories on an EC2 instance using VS Code.

### Project reflection

I did not expect it to be a bit challenging as someone with a tech background.

This project took me approximately 3 hours. The most challenging part was Java JDK and JRE on ubuntu. These were not easy to install opted to use AMZN linux. It was most rewarding to finally connect to the instance and edit the index.jsp file.

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in about 3 hours.

---

## Launching an EC2 instance

Because this is where the DevOps challenges will be hosted.

### I also enabled SSH

SSH is a protocol used to connect to EC2 instance in the cloud. I enabled SSH so that I can connect to my EC2 instance.

### Key pairs

A key pair is a file used to securely access the EC2 instance. This file comes in sets of two, the public and private. AWS keeps the public one and you keep the private one. When conencting with the private one AWS matches it to the public one it has

Once I set up my key pair, AWS automatically downloaded the key pair with the .pem extension usable with OpenSSH 

---

## Set up VS Code

VS Code is an IDE used to write code, but could also be used to conenct to an EC2 instance.

I installed VS Code to change the file permissions on the key file.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is an interface were you send instructions to your computer in the form of text instructions instead of clicks.

I first reset the file permissions, then after than gave read permissions to myself. Then made sure permission changes in the other files will not affect our key file.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

To connect to my EC2 instance I used the ssh command and speicfied the key path, username(in this case ubuntu) and the EC2 address.

### This command required an IPv4 address

A server's IPv4 DNS is an address the the server uses to to to the internet.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

Apache Maven is a tool that automates the building of software.

Maven automate compiling, linking testing and packaging.

Java is a popular programming language used to build different types of applications from mobile to large enterprise solutions.

Java is required for this project because we will be using it to build our web app and its highly compatible with Apache. 

---

## Create the Application

I created the Java web app using the command mvn archetype:generate \
   -DgroupId=com.nextwork.app \
   -DartifactId=nextwork-web-project \
   -DarchetypeArtifactId=maven-archetype-webapp \
   -DinteractiveMode=false


It will allow us to edit and update the web app files easily.

COnfiguration details required to set up a remote connection include the hostname, key path and the username to user for login.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

Using VS Code's file explorer, I could see the directories and files of my web app.

Two of the project folders created by Maven are src and webapp, of which webapp is the subfolder that contains the HTML, CSS, Javascript and JSP files required by the application.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

index.jsp is a file similar to html used by java web applications.

I edited index.jsp by using Ctrl + S to save the file.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

---

---
