<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a GitHub Repo with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-github)

**Author:** Rawley Chirume  
**Email:** chirumerawley@gmail.com

---

## Connect a GitHub Repo with AWS

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-github_dd9d254e)

---

## Introducing Today's Project!

Today we are connecting AWS to a Github repo.

### Key tools and concepts

Services I used were Git and GitHub. Key concepts I learn t include setting up a local repo, connecting the repo to GitHub origin, pushing changes via access tokens.

### Project reflection

This project took me approximately an hour. The most challenging part was that my EC2 instance would freeze up because I was installing Java extensions in VS Code.

I did this project to progress with my DevOps challenge to Day 3. This project did meet my goals of learning how to use git and GitHub.

This project is part of the DevOps projects where I am building a CI/CD pipeline! I will be working o nth next project in about 5 hours.

---

## Git and GitHub

Git is a tool used to track versions of your code by keeping the history of every changes made.

Github is a storage space for different versions of your code that Git keeps track of.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-github_efaadbf7)

---

## My local repository

A Git repository is a folder that stores our web app's files and tracks all the version history including all code changes.

git init is a command tha initializes my current opened folder as a local repository. Now that means any changes to the porject can be tracked for version control. I ran git init in the nextwork-web-project folder.

After running git init, the response from the terminal was that my inital branch is called master but this can be changed to main, devel or any other word I would like.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-github_7bf21bae)

---

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was 'git add .', this stages all files in the project to be saved to the next version of the project. A staging area is where I can see all changes made in the project in one place.

### git commit

The second command I ran was 'git commit -m "Updated index.jsp..."'. Using '-m' means that you would like to leave a note describing what the commit is about.

### git push

The third command I ran was 'git push -u origin master'. Using '-u' means I am telling git to remember which branch and origin to always upload my changes to... in the is case, the origin we defined earlier, and the master branch created earlier.

---

## Authentication

When I commit changes to GitHub, Git asks for my credenitals because it needs to check whether I have permission to push changes to the repository.

### Local Git identity

Git needs my name and emai because it needs to indentify who is pushing which commits. 

Running git log showed me that my name has been set to "EC2 Default User" and the email address is randomly generated.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-github_9a27ee3b)

---

## GitHub tokens

GitHub authentication failed when I entered my password because password auth over HTTPS was phased out a while back because of the security risks associated with sending your passwords over the internet.

A GitHub access token is a unique string of characters that looks like a random passowrd. I am using one in this project because it will allow me to push my changes to my GitHub repository and is safer than plain passwords.

I could setup a GitHub token by generating one in the GitHub settings.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-github_fa11169d)

---

## Making changes again

I wanted to see Git working in action so I updated the index.jsp file.

I finally saw the changed in my GitHub repo after pushing the local changes to GitHub.

![Image](http://learn.nextwork.org/encouraged_beige_beautiful_goat/uploads/aws-devops-github_6becb2bc)

---

## Setting up a READMe file

---

---
