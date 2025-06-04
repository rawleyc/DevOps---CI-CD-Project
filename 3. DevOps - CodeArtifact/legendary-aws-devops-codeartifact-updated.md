<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Secure Packages with CodeArtifact

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codeartifact-updated)

**Author:** Rawley Chirume  
**Email:** chirumerawley@gmail.com

---

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codeartifact-updated_1d79e699)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create a CodeArtifact repository.

### Key tools and concepts

Services I used were CodeArtifact, IAM (roles & policies). Key concepts I learnt include IAM roles and policies, also how they can be connected to CodeArtifact and EC2 instances.

### Project reflection

This project took me approximately 2 hours to complete. The most challenging part was creating the IAM policies and roles, the pace of the instructions was quicker there.

This project is part of a series of DevOps projects where I am building a CI/CD pipeline! I'll be working on the next project tomorrow.

---

## CodeArtifact Repository

CodeArtifact is a secure, central place to store all your software packages. Engineering teams use artifact repositories because you can share and use the same versions of packages when building projects.

A domain is like a folder that holds many repos. It give us one place to manage permissions and security. My domain is 'nextwork'

A CodeArtifact repository can have an upstream repository, whih means that if my project looks for a library in the CodeArtifact and cannot find it, it will be retrieved from the upstream repo. My repository's upstream repo is Maven Central.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codeartifact-updated_n4o5p6q7)

---

## CodeArtifact Security

### Issue

To access CodeArtifact we need an authorizatin token to allow the EC2 instance to access my AWS services. I ran into an error when retrieving a token because I do not have permission to access my AWS services from the EC2 instance.

### Resolution

To resolve the error with my security token, I created a new IAM policy, and then attached this policy to a new role created. Then this new role was attached to the EC2 instance.

It's security best practice to use IAM roles because AWs automatically provides and rotates temporary security credentials for that instance.

---

## The JSON policy attached to my role

The JSON policy I set up grants access to read the CodeArtifact repository.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codeartifact-updated_23rp7q8r9)

---

## Maven and CodeArtifact

### To test the connection between Maven and CodeArtifact, I compiled my web app using settings.xml

The settings.xml file configures Maven to look in specific repositories for packages and how to behave should it not find the package.

Compiling is like translating the project's code into code that the machines can understand.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codeartifact-updated_c17eace8)

---

## Verify Connection

After  compiling my app, I checked the CodeArtifact repository and noticed that I now have packages stored there.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-codeartifact-updated_1d79e699)

---

## Uploading My Own Packages

---

---
