# Continious Integration and why you should use it

Every developer has been in the situation where they have to deploy a webapp. Doing this manually can lead to inconsistency and mistakes. This is where setting up your ‘continuous integration’ with Jenkins can help you a lot. Setting up jenkins is easier than you might have thought, and your knowledge of it should not stop you from getting a completely autonomous deployment chain.

We want to show, that setting up a CI chain can be both easy and painless. Even if you have no knowledge of it beforehand and even if you are students such as ourselves, that you can with relative ease setup Jenkins.


1. Hvad er CI
  - blabla
  - pro/cons i forhold til manuel
2. Jenkins
  - hvad er jenkins
  - hvad er jenkins godt til
  - requirements
3. Pros / cons for CI over manuel
https://www.tutorialspoint.com/jenkins/jenkins_overview.htm
https://en.wikipedia.org/wiki/Continuous_integration 


## How to install Jenkins
To begin working with jenkins, we need three things.
1. A DigitalOcean account, https://www.digitalocean.com/
2. git, https://git-scm.com/
3. putty, a tool to connect to our host (linux users do not need this tool), http://www.putty.org/ 
<br>Now when we have these things ready, we need a public and a private key, this is used to connect to your host.
<p align="center"><a  href="http://www.youtube.com/watch?feature=player_embedded&v=T9qTWAG8s-E" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/final.gif" align="center" alt="ssh key pair" width="50%" height="50%" border="10"></a></p>

<br>Now we need a droplet (other web hosts can be used but we will be using digitalocean.com for this example, if you are a student you can get a 50 dollar coupon, among other things, via github.com, https://education.github.com/pack.
<br>remember to add your private key when initializing the droplet.
<p align="center"><a  href="http://www.youtube.com/watch?feature=player_embedded&v=pFwREmUMz64" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/DO_screenshot.png" align="center" alt="ssh key pair" width="50%" height="50%" border="10"></a></p>
<p align="center"><a  href="https://youtu.be/pFwREmUMz64" target="_blank"><img src="https://github.com/Thug-Lyfe/UFO_Blog/blob/master/src/DO_screenshot.png" align="center" alt="ssh key pair" width="50%" height="50%" border="10"></a></p>

<br>Now open putty and connect to your droplet and install jenkins
<br>“video of installing jenkins”
<br>now you have your jenkins running, if you are using github, you can add a webhook and use it in jenkins.
<br>“gif of creating and using the webhook”

## Why don't we see more Jenkins?
Well if jenkins is so good, why are there not more people using it? Well first of all jenkins is not for everyone, nor is it omnipotent, eg. people who are using platforms such as wordpress or other webapp creators, will not find much use for it, as they have CI build into it. But for everyone making their own webapp from scrap, even if it is for a local network, it can work splendidly.
<br>Another reason is that it costs money, if you have it hosted on digitalocean.com it will cost a minimum of 10 dollars a month, and that can be a solid reason for many small time business owners, or private people to not opt for using it.

### conclusion
Anyone who has to deal with manual deployment, should think about setting up a CI chain. It can not be said enough, that manual deployment leads to irregular deployments, mistakes, missed steps in the deployment chain and so on. <br>Having an autonomous deployment, will make it both easier and better for all partners involved.




img[src$="centerme"] {
  display:block;
  margin: 0 auto;
}