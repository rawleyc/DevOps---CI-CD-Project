<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Deploy a Web App with CodeDeploy

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codedeploy-updated)

**Author:** Rawley Chirume  
**Email:** chirumerawley@gmail.com

---

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codedeploy-updated_val-27)

---

## Introducing Today's Project!

In his project, I will demonstrate how to use AWS CloudDeploy to continously rollout apps to users and also rollback changes should there need to.

### Key tools and concepts

Services I used were CodeDeploy, S3, IAM, CodeBuild, and EC2. Key concepts I learnt include the accepted syntax of the YAML files. The other was the structure of the commands and keys in the YAML files, so yeah, syntax.

### Project reflection

This project took me more than 4 hours to complete. The most challenging part was noticing the pre-build key that was nested in the commands key, which is not allowed... 'key -> lines of commands' NOT 'key -> key'

This project is part five of a series of DevOps projects where I am building a CI/Cd pipeline! I'll be working on the next project in 5 - 6 hours.

---

## Deployment Environment

To setup for Code Deploy, I lanched an EC2 instance and VPC because it was specified in the CloudFormation stack.

Instead of launching these services manually, I used AWS CloudFormation. When I need to delete these resources, I can just rollback my stack created in AWS CloudFormation.

Other resources being created in this template include, IAM roles, subnets and security groups. They're also in this template because our WebServer EC2 instance will have seperate settings from the devops instance.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codedeploy-updated_val-5)

---

## Deployment Scripts

Scripts are step by step instructions that run commands one by one and may be connected to one another. To set up CodeDeploy I also wrote scripts that installed the dependencies needed by our project.

install_dependencies.sh will install the program required by our application to function and be accessible on the internet.

start_server.sh will start both Apache and Tomcat and make sure they restart automatically if our EC2 instance ever reboots.

stop_server.sh attempts to stop the application only if Tomcat and Apache are running. If not then that mean our application is not running.

---

## appspec.yml

Then, I wrote an appspec.yml file to provide instructions for CodeDeploy to follow when deploying our application.

I also updated buildspec.yml because we need to include the scripts in the final package of the application. So, hence we edited the instructions for CodeBuild.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codedeploy-updated_val-12)

---

## Setting Up CodeDeploy

A deployment group contains the resources assign or reserved for an application or for something to be deployed using them.

To set up a deployment group, you also need to create an IAM role to give permissions to CodeDeploy to access AWS services required by your application on your behalf like S3 for fetching the application itself. 

Tags are helpful for identifying what the resource is being used for and I used the tag to group all resources tagged webserver in one deployment group.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codedeploy-updated_val-18)

---

## Deployment configurations

Another key setting is the deployment configuration, which affects the number of EC2 instances to which we deploy our application. I used CdoeDeployDefault.AllAtOnce, so my app is deployed to all instances at the same time.

In order to connect EC2 instances with CodeDeploy, a CodeDeploy Agent is the one used to execute the scripts. It is also setup to check for updates every 14 days to avoid any bug in deployment.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codedeploy-updated_val-20)

---

## Success!

A CodeDeploy deployment is a single update to my application with its own history and ID.

I had to configure a revision location which means the location where CodeDeploy can find my artifact. My revision location was my S3 bucket.

To check that the deployment was a success, I visited the public IPv4 address of the EC2 instance. I saw that the application was now accessible.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codedeploy-updated_val-27)

---

## Disaster Recovery

---

---
