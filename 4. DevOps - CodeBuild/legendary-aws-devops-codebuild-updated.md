<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Continuous Integration with CodeBuild

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codebuild-updated)

**Author:** Rawley Chirume  
**Email:** chirumerawley@gmail.com

---

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codebuild-updated_35588a47)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use CodeBuild to automate the building process of our project. I am doing this project to learn how CodeBuild is intergrated in the CI/CD pipeline.

### Key tools and concepts

Services I used were, CodeArtifact and CodeBuild, I also used IAM service to mange roles.

### Project reflection

This project took me approximately 4 hours, but over a few days due to school and work.. The most challenging part was the buildspec.yml file, as it very vague.

This project is part four of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project soon...

---

## Setting up a CodeBuild Project

CodeBuild is a continuous intergration service, which means that it is like a checkpoint that my code goes through everytime I push any new changes to the code.

My CodeBuild project's source is the location where CodeBuild can fetch my project code from in order to compile it.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codebuild-updated_fewgrhte)

---

## Connecting CodeBuild with GitHub

There a re multiple credential types for GitHub, like GitHub app and OAuth. I used GitHub app because it is simpler and more secure to use and setup.

The service that helped connect is Code Connection.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codebuild-updated_a7c98e2d)

---

## CodeBuild Configurations

### Environment

My CodeBuild project's enviroment configuration means the settings used everytime CodeBuild runs and builds my project files.

### Artifacts

Build arifacts are the products of the build process. They're important because they are what we will actually distribute to users. To store them, I created an S3 bucket.

### Packaging

When setting up CodeBuild, I also chose to package artifacts in a zip file because zip files take less storage and hence reduce costs and they're also easier to share.

### Monitoring

For monitoring, I enabled CloudWatch Logs, which is a service that monitors the AWS services used my my project including the commands ran and all the output along withthe errors.

---

## buildspec.yml

My first build failed because the buildspec.yml file was not found. A buildspec.yml file is needed because it contains the commands to run throughout the build process.

The first two phases in my buildspec.yml file configure and einviroment and make sure the build process will be smooth. The third phase is when the actual building starts. The fourth phase packages the product of the build process into our WAR file.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codebuild-updated_35588a47)

---

## Success!

My second build failed, but with a different error that said that CodeBuild cannot access my settings.xml file. To fix this, we will give CodeBuild permission to access CoderArtifact.

To resolve the second error, I attached new policies to the IAM fole used by CodeBuild to give it permission to access CodeArtifact. I also configured the buildspec.yml to use my region and domain owner and domain.

To verify the build, I checked my bucket and saw the uploaded artifact. Seeing the artifact tells me the build process was a success.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codebuild-updated_d9cc6191)

---

## Automating Testing

---

---
