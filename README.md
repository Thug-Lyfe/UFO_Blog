# Continious Integration and why you should use it
---
### Authors
Marco S. Blum

Christian Lind

---
*Every developer has been in the situation where they have to deploy a webapp. Doing this manually can lead to inconsistency and mistakes. This is where setting up your ‘continuous integration and deployment’ with Jenkins can help you a lot. This is a guide for fellow students or people who would like to know more about setting up a CI/CD chain and how it can be both easy and painless.*

---

### What is CI?
A simple change to a single file can easily have unintended consequences to a working repository. This can result in merging conflicts or integration problems. CI is most often used in the effort of alleviating those problems. 

The practice of continuous integration<a name="ref1">[<sup>[**1**]</sup>](#end1)</a><a name="ref2">[<sup>[**2**]</sup>](#end2)</a> is the process of committing and integrating code, to a shared repository more frequently during the working process. Which is most often followed by automated unit and integration tests, to make certain, the code is up to standard. This leads to less merging conflicts, since the commits are smaller and less comprehensive. It also provides the developers, with a faster feedback, which leads to better and faster written code.

### What is Continuous Delivery 
Continuous delivery <a name="ref3">[<sup>[**3**]</sup>](#end3)</a> is an extension of continuous integration, Where continuous delivery focuses more on delivering code rapidly and safely to a production environment. All the newly added code will be added to a testing environment where it will not only be submitted to automated unit, integration tests, but also functional tests and more. This in turn means that the developer or the owner is 100% sure that the code works and can be deployed with relative ease.


<p align="center"><img src="https://puppet.com/sites/default/files/2016-09/puppet_continuous_diagram.gif" alt="delivery vs deployment" width="50%" height="50%" border="10"></p> 




*Diagram showcasing delivery and deployment* <a name="ref4">[<sup>[**4**]</sup>](#end4)</a>




### What is Continuous Deployment 
Continuous deployment<a name="ref5">[<sup>[**5**]</sup>](#end5)</a> is an extension of continuous delivery. However, it focuses on fully automating not only the testing environment, but also the deployment, so that each commit is deployed automatically after it has passed all the delivery tests. This minimizes the amount of time a devops or developer has to work to get the webapp to live, and leads to an overall performance boost. In Jenkins you can set ssh keys up between jenkins and the host, so that it logs in and deploys the webapp by itself, everytime a new version of the code is live. 

Continuous deployment<a name="ref4">[<sup>[**4**]</sup>](#end4)</a> isn’t suitable for just any company. It is not everyone who wants the newest iteration of the website to go live the minute it’s made. Though continuous delivery is an absolute must, if the developer is seperate from the owner of the website. Since this means the owner can, at all times, deploy the newest version when it has reached a suitable state. Also the developer doesn’t have to deal with presenting and testing, but can solely focus on contributing more work to improve the platform.


### Jenkins 

Jenkins<a name="ref6">[<sup>[**6**]</sup>](#end6)</a> is a software which operates as an automated server, running on servlet containers, that allows continuous integration.

These following steps will showcase how Jenkins works during a workflow:
- Developers check their source code
- Jenkins will pick up the changed source code, then trigger a build to run any test, if required.
- The build output will be available in the Jenkins dashboards.
<p align="center"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/jenkins_diagram.png" alt="jenkins diagram" width="50%" height="50%" border="10"></p>

#### Requirements 

There are next to no requirements for jenkins. All the user needs is<a name="ref7">[<sup>[**7**]</sup>](#end7)</a>: 
- JDK 1.5 or above
- A droplet with min 1GB of ram though 2 GB is recommended
- Any operating system

#### Pro / cons for Jenkins

- Pros
  - It’s distributed
  - It’s easy to install
  - It’s easy to configure
- Cons
  - It costs money
  - Takes time to configure and set up

### Pros for CI over manual integration

- Issues caught early
- The waiting to see if one members code works won’t be there as it will be tested and built as it gets committed
- It’s automated
- Makes it easier for deployment

---
## How to install Jenkins
note: the images are links to the full youtube clips.
<br>
<br>To begin working with jenkins, we need three things.
1. A DigitalOcean account, https://www.digitalocean.com/
2. git, https://git-scm.com/
3. putty, a tool to connect to our host (linux users do not need this tool), http://www.putty.org/ 
<br>Now when we have these things ready, we need a public and a private key, this is used to connect to your host.
<p align="center"><a  href="https://youtu.be/pFwREmUMz64" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/key.gif" align="center" alt="ssh key pair" width="50%" height="50%" border="10"></a></p>

<br>Now we need a droplet (other web hosts can be used but we will be using digitalocean.com for this example, if you are a student you can get a 50 dollar coupon, among other things, via github.com, https://education.github.com/pack.
<br>remember to add your private key when initializing the droplet.

<p align="center"><a  href="https://youtu.be/pFwREmUMz64" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/DO.gif" align="center" alt="droplet creation" width="50%" height="50%" border="10"></a></p>

<br>Now open putty and connect to your droplet and install jenkins
<p align="center"><a  href="https://youtu.be/4b_OvbeQYko" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/jenkins_install.gif" align="center" alt="jenkins installation" width="50%" height="50%" border="10"></a></p>
The lines to paste into your putty window is as following:
<br> 1. sudo apt-get update
<br> 2. sudo apt-get install default-jre
<br> 3. sudo apt-get install default-jdk
<br> 4. sudo wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
<br> 5. sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
<br> 6. sudo apt-get update
<br> 7. sudo apt-get install jenkins
<br> Jenkins is now running and can be accessed on "YOUR_IP":8080
<br>We can now use a repository on github, where we can add a webhook and use it in jenkins.
<br>On your github repository you can add a jenkins servive, and in the jenkins you can install a a github integration plugin and your good to go.
<br>Add an item and link it to your github and use the build trigger to use your webhook and run what you want.

---
<br>

## Alternatives… 
Well Jenkins is all fine and dandy, but what about other software<a name="ref8">[<sup>[**8**]</sup>](#end8)</a> that can be used to make a CI/CD chain?

There are many tools for making a CI/CD chain, too many to test them all. So we have gathered what we think is some of the better ones, if they are better is up for to you to decide.

### GitLab Ci
While Jenkins needs to be setup with a github repository to get a CI/CD working, GitLab is on the other hand set up without github. When GitLab is installed you can create git projects on the GitLab server and push your code to your own server directly instead, this means that with a bit of security in place you can have your own private github server. It is both open source and has many features that make CI/CD chain swift to set up.
If you want to check out how to install it go <a name="ref9">here[<sup>[**9**]</sup>](#end9)</a> , if you want to know how others feel about the two tools you can go <a name="ref10">here[<sup>[**10**]</sup>](#end10)</a>, 

### Teamcity

Teamcity<a name="ref11">[<sup>[**11**]</sup>](#end11)</a> is a java-based CI server package that has a simple, quick and easy configuration and installation. It has a great interface and helpful features for getting started with continuous integration. However, all around it might be the better alternative, but it’s not an open-source software as jenkins, nor is it free. After the initial 100 builds, where a webapp usually needs a couple for various things, it is 300 euro for 10 builds extra and 2000 euro for unlimited build configurations, and it only escalates with the number of threads you need or want.

We will suggest you to check out a few others, such as: 
- Buildbot https://buildbot.net
- Concourse https://concourse.ci 
- Travis CI https://travis-ci.org 


If you are interested in other alternatives check out:
https://www.infostretch.com/blog/39-tools-for-building-your-cicd-stack/ or 
https://stackify.com/top-continuous-integration-tools/ 

---

## So what about CI? Who even bothers with Jenkins?
Well Jenkins is pretty well spread in the industry as it is both robust and open source, of course there some things it could improve, like default ports and plugins that need the entire jenkins server to restart etc. But there are some big companies out there who use it such as<a name="ref12">[<sup>[**12**]</sup>](#end12)</a>  : ebay, yahoo, linkedin, netflix, nintendo, tumblr, even the uk government uses jenkins. 
While we are certainly not a big company it has been a relative a a good experience to use it for personal websites and school projects.
Jenkins has even reached more than 100.000 Active installations worldwide<a name="ref13">[<sup>[**13**]</sup>](#end13)</a>.  


---
## References   
<a name="end1">[<sup>[**1**]</sup>](#ref1)</a> *https://en.wikipedia.org/wiki/Continuous_integration - *

<a name="end2">[<sup>[**2**]</sup>](#ref2)</a> *https://www.visualstudio.com/learn/what-is-continuous-integration/ - *

<a name="end3">[<sup>[**3**]</sup>](#ref3)</a> *https://blog.assembla.com/assemblablog/tabid/12618/bid/92411/continuous-delivery-vs-continuous-deployment-vs-continuous-integration-wait-huh.aspx - *

<a name="end4">[<sup>[**4**]</sup>](#ref4)</a> *https://puppet.com/blog/continuous-delivery-vs-continuous-deployment-what-s-diff  - *

<a name="end5">[<sup>[**5**]</sup>](#ref5)</a> *http://searchsoftwarequality.techtarget.com/definition/Continuous-Software-Development - *

<a name="end6">[<sup>[**6**]</sup>](#ref6)</a> *https://en.wikipedia.org/wiki/Jenkins_(software) - *

<a name="end7">[<sup>[**7**]</sup>](#ref7)</a> *https://www.tutorialspoint.com/jenkins/jenkins_overview.htm - *

<a name="end8">[<sup>[**8**]</sup>](#ref8)</a> *https://www.digitalocean.com/community/tutorials/ci-cd-tools-comparison-jenkins-gitlab-ci-buildbot-drone-and-concourse - *

<a name="end9">[<sup>[**9**]</sup>](#ref9)</a> *https://www.codereviewvideos.com/course/your-own-private-github/video/zero-to-gitlab-in-5-minutes - *

<a name="end10">[<sup>[**10**]</sup>](#ref10)</a> *https://www.slant.co/versus/2477/2482/~jenkins_vs_gitlab-ci - *

<a name="end11">[<sup>[**11**]</sup>](#ref11)</a> *https://www.upguard.com/articles/teamcity-vs.-jenkins-for-continuous-integration  - *

<a name="end12">[<sup>[**12**]</sup>](#ref12)</a> *https://wiki.jenkins.io/pages/viewpage.action?pageId=58001258 - *

<a name="end13">[<sup>[**13**]</sup>](#ref13)</a> *https://www.cloudbees.com/press/jenkins-community-reaches-milestone-more-100000-active-installations-worldwide - *


<br> https://youtu.be/T9qTWAG8s-E - ssh key creation
<br> https://youtu.be/pFwREmUMz64 - Digital ocean droplet create
<br> https://youtu.be/4b_OvbeQYko - Jenkins installation video
