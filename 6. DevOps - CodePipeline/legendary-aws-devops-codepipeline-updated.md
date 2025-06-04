<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a CI/CD Pipeline with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codepipeline-updated)

**Author:** Rawley Chirume  
**Email:** chirumerawley@gmail.com

---

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Introducing Today's Project!

In this project, I will demonstrate automated deployments in action. I'm doing this project to learn the structure of a CI/CD pipeline and it's advantages.

### Key tools and concepts

Services I used where Git, CodePipeline, GitHub, Security groups and EC2. Key conencepts I learnt was how webhooks are used to listen to repo events and also how to connect GitHub, CodeBuild, and CodeDeploy all in CodePipeline.

### Project reflection

This project took me approximately 2 hours. The most challenging part was getting the webpage to load, had to modify security groups and all it needed was to use http instead of https.

---

## Starting a CI/CD Pipeline

AWS CodePipeline is a service that automatically moves your project though build and deployment stages. It can detect a new push to the github repository and start the build and finally deploy the project.

CodePipeline offers different execution modes based on the time a build is triggered. I chose Superseded, because it means only the latest changes will be processed even if two build are triggered... only the latest will succeed.

A service role gets created automatically during setup so that CodePipeline can act on my behalf, hence will have access to other services such as S3, and EC2.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_gdnhtm)

---

## CI/CD Stages

The three stages I've set up in my CI/CD pipline are Source, Build and Deploy. While setting up each part I learnt about how GitHub, CodeBuild and CodeDeploy are all connected in the pipeline.

CodePipeline organizes the three stages into Source, Build and Deploy. In each stage, you can see more details on the status of the execution, whether the stage has started, is in progress, has succeeded or has failed.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Source Stage

In the Soure stage, the default branch tells CodePipeline when there are new changes and triggers a build.

The source stage is also where you enable webhook events, which act like notifications. So this webhook is designed to listen for events such as pushes to my GitHub repo so. When a push occurs a webhook is sent from GitHub to CodePipeline.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_sergt)

---

## Build Stage

The build stage sets up using the SourceArtifact outputted from the Source stage. The input for the build stage is the SourceArtifact which is basically a ZIP file of our code.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_j1k2l3m4)

---

## Deploy Stage

The Deploy stagge is where the BuildArtifact is deployed to the EC2 instances and the application goes live.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_m4n5o6p7)

---

## Success!

Since my CodePipeline gets triggered by code changes to my GitHub repo, I tested my pipeline by introducing a code change in the index.jsp file.

The moment I pushed the code change the CodePipleine started to execute. The commit message under each stage reflects the commit message in the GitHUb repo submitted with the code change that triggered the build.

Once my pipline executed successfully I checked the application and it had implemented the changes in the code.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codepipeline-updated_e1f2g3h4)

---

## Testing the Pipeline

---

---
