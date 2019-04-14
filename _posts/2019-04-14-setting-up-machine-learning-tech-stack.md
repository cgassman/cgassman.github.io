---
layout: post
title: "Setting up machine learning tech stack"
date: 2019-04-14
---

Setting up a centrally managed technical stack for machine learning in an enterprise environment brings some extra challenges.
As expected it is much easier to set up a single-user on a private environment: using anaconda community edition for example provides an easy start, jupyternotebooks and beside conda pip install to get everything that might or might not be required and I was good to start.

But what is required in an enterprise environment?
On the one side, several users collaborating on the same notebooks, requesting for an R as well as a Python stack, leaving as much flexibility as somehow possible to download and install packages from pip etc. Exposing models through web services. 
On the other side, security setting up firewalls and proxies controlling traffic and programs running, minimizing the risk to import/download malicious code into the protected zone. Regulatory requirements, asking the enterprise to be able to list the models in place (e.g. for reasons of personal data protection), not only for one business but for the whole enterprise. Operations which needs to support the different stacks and therefore needs to know which packages and which versions are used for maintenance and upgrade reasons. 

Overall, we wanted to start off with machine learning, not having clear business cases, that pay-off yet. So there were only investments and no clear or concrete benefits yet. This meant we had to start with an absolute bare minimum. Finding a way of a minimal managed technical stack, enabling machine learning in a somehow managed way, with minimal or no additional expenses...   

As we use anaconda and jupyternotebooks / jupyterlab for private data science experiences, it was a logical conclusion to us, to start with the very same tools in the enterprise environment. It was the best starting position we had, but it showed quite soon, that this approach won't result in the required outcome. In concrete, we faced the following issues when we started:  

* Anaconda community edition requires a connection to its central repo, which wasn't appreciated by our proxies.  
* Redhat Enterprise Edition didn't seem to be compatible with Docker Community Edition.  
* Jupyternotebook or jupyterlab didn't allow multi-users on the same notebook.    

Stepwise we tried to find an ideal solution. It doesn't have to be optimal, ideal for our purposes and given limitations would be great already.
 

Collection of most important linux commands, used to or useful when setting up a technical stack for machine learning in an enterprise environment.  

|Command     |Description         
|------------|-------------------------------------------------------------------------
|            |
|