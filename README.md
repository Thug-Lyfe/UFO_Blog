# Continious Integration and why you should use it
---
Every developer has been in the situation where they have to deploy a webapp. Doing this manually can lead to inconsistency and mistakes. This is where setting up your ‘continuous integration’ with Jenkins can help you a lot. Setting up jenkins is easier than you might have thought, and your knowledge of it should not stop you from getting a completely autonomous deployment chain.

We want to show, that setting up a CI chain can be both easy and painless. Even if you have no knowledge of it beforehand and even if you are students such as ourselves, that you can with relative ease setup Jenkins.


1. What is CI

Every developer knows the struggle of merging. A simple change to a single file can easily have unintended consequences to a working repository. This results in development teams working isolated from each other, even as far to be working on their own separate branches of the master, to prevent getting tangled up in each other’s work.
Development teams that are working on branches that hasn’t been integrated to the master,  often requires phases of stabilization and integration, prior to a release.
The practice of continuous integration addresses these problems and is being used to encourage development teams to commit and integrate their code, to a shared repository more frequently doing the working process. When a developer commits code to the shared repository, an automated build will be triggered to grab the code and start a build, tests and validations of the full master branch. It’s used to identify and fix mistake faster, which then increases the productivity.

2. Jenkins

Jenkins is a software which operates as an automated server, running on servlet containers, that allows continuous integration.

These following steps will showcase how Jenkins works during a workflow:
- Developers check their source code
- Jenkins will pick up the changed source code, then trigger a build to run any test, if required.
- The build output will be available in the Jenkins dashboards.

2.1 Requirements

There are next to no requirements for jenkins. All the user needs is: 
- JDK 1.5 or above
- A droplet with min 1GB of ram though 2 GB is recommended
- Any operating system

2.3 Pro / cons for Jenkins

- Pros
  - It’s distributed
  - It’s easy to install
  - It’s easy to configure
- Cons
  - It costs money
  - Takes time to configure and set up

3. Pros / cons for CI over manual integration

- Issues caught early
- No merge conflicts
- The waiting to see if one members code works won’t be there as it will be tested and built as it gets committed
- It’s automated
- Makes it easier for deployment


## How to install Jenkins
To begin working with jenkins, we need three things.
1. A DigitalOcean account, https://www.digitalocean.com/
2. git, https://git-scm.com/
3. putty, a tool to connect to our host (linux users do not need this tool), http://www.putty.org/ 
<br>Now when we have these things ready, we need a public and a private key, this is used to connect to your host.
<p align="center"><a  href="https://youtu.be/pFwREmUMz64" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/final.gif" align="center" alt="ssh key pair" width="50%" height="50%" border="10"></a></p>

<br>Now we need a droplet (other web hosts can be used but we will be using digitalocean.com for this example, if you are a student you can get a 50 dollar coupon, among other things, via github.com, https://education.github.com/pack.
<br>remember to add your private key when initializing the droplet.

<p align="center"><a  href="https://youtu.be/pFwREmUMz64" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/DO_screenshot.png" align="center" alt="droplet creation" width="50%" height="50%" border="10"></a></p>

<br>Now open putty and connect to your droplet and install jenkins
<p align="center"><a  href="https://youtu.be/4b_OvbeQYko" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/jenkins_screenshot.png" align="center" alt="jenkins installation" width="50%" height="50%" border="10"></a></p>
The lines to paste into your putty window is as following:
<br>1. sudo apt-get update
<br>2. sudo apt-get install default-jre
<br>3. sudo apt-get install default-jdk
<br>4. sudo wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
<br>5. sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
<br>6. sudo apt-get update
<br>7. sudo apt-get install jenkins
<br> Jenkins is now running and can be accessed on "YOUR_IP":8080
<br>We can now use a repository on github, where we can add a webhook and use it in jenkins.
<br>on your github repository you can add a jenkins servive, and in the jenkins you can install a a github integration plugin and your good to go.
<br> add an item and link it to your github

<br>## Why don't we see more Jenkins?
Well if jenkins is so good, why are there not more people using it? Well first of all jenkins is not for everyone, nor is it omnipotent, eg. people who are using platforms such as wordpress or other webapp creators, will not find much use for it, as they have CI build into it. But for everyone making their own webapp from scrap, even if it is for a local network, it can work splendidly.
<br>Another reason is that it costs money, if you have it hosted on digitalocean.com it will cost a minimum of 10 dollars a month, and that can be a solid reason for many small time business owners, or private people to not opt for using it.

### conclusion
Anyone who has to deal with manual deployment, should think about setting up a CI chain. It can not be said enough, that manual deployment leads to irregular deployments, mistakes, missed steps in the deployment chain and so on. <br>Having an autonomous deployment, will make it both easier and better for all partners involved.



