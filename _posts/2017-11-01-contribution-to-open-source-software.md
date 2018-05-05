---
layout: post
title: "Contribution to Open Source Software (OSS)"
date: 2017-11-01
---

This month is dedicated to two topics: make first steps in contributions to open source software (oss) as well as improve my Python programming skills. The first objective regarding open source software was triggered by a podcast called "Happy Hacktoberfest" on October 15, 2017 by [Linear Digressions](http://lineardigressions.com/). This podcast was about the importance of open source software and how you can get involved. The second objective is to find out, how programming skills can be impproved and also trying to find out tips and tricks on what good programming style is.  

## Getting started with open source contribution  
Curious how contribution to open source project works, so many open questions: where can I find projects looking for contributors? what kind of contributions are required? what skills do I need to bring along? does a contributor need to be a world-renowned coder :-S ? how does a contribution finally work, so which steps are needed to make a contribution? I wonder if I can overcome (at least some) of currently intimidating barriers.  

Based on an internet research the following websites seem to be a good starting point 

- [OpenHatch](http://openhatch.org/). Providing online tools and education for new contributors. Step by step introduction to diff and patch, how to interact with projects that use the Git version control system etc. 
- [hackerearth](https://www.hackerearth.com/getstarted-opensource/). Summarizing how to get started with Open Source.  
- [GitPro](https://git-scm.com/book/en/v2) in general, but especially chapter 6.2 [GitPro - Contributing to a Project](https://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project)
- [Getting into open source for the first time](https://www.nearform.com/blog/first-time-with-open-source/) step by step guide, written by Dean McDonnell. Very useful to get an understanding on the various git commands and in which sequence they need to be applied. 
- [up for grabs](http://up-for-grabs.net/#/) is a site listing open source projects for new contributors

### Actions and conclusion:

- Running through the [OpenHatch](http://openhatch.org/) missions: when creating a tar file. Verify that no hidden files are 'automatically' be imported. Use COPYFILE_DISABLE=true  
- wanted to start with contributing to a project listed on [up for grabs](http://up-for-grabs.net/#/) but didn't understand how pull request, issues, fork etc. are connected. I was still missing some basic concepts.       
- chapter 6.2 [GitPro - Contributing to a Project](https://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project) as mentioned above was very helpful to understand how Git works, what is meant by fork and pull-requests, how things are connected and how contribution over Git as a code repository works.   
- read [Getting into open source for the first time](https://www.nearform.com/blog/first-time-with-open-source/)    
- Thanks to these two resources just mentioned above I could overcome one of my biggest 'fears' which was '...what if I destroy the author's project...' even if this sounds silly, this was the most important question I had: 'How is the original work protected and given this protection, how does contribution work?'. [GitPro - Contributing to a Project](https://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project) as well as [Getting into open source for the first time](https://www.nearform.com/blog/first-time-with-open-source/) provided me the answer. fork, clone, branch and you're safe for now, curious on the way back after changes will be implemented, but let this question rest for now     
- grabbed a project on [up for grabs](http://up-for-grabs.net/#/). Focused on a 'fix spelling errors' issue of a project and walked through the [Getting into open source for the first time](https://www.nearform.com/blog/first-time-with-open-source/) to get started. 
- fixed two spelling errors, added to staging area, commited to local repository and pushed my branch up to my forked repository.
- now starts the next part where I'm getting nervous: creating a pull request :-S
- seeing that my branch is ahead (and luckily not behind), clicked on the 'pull request' button, beautified comment, committed pull request and now await feedback from the author/owner. Hopefully, everything got well, the feedback can be used and didn't wreck anything.   


---  

## Improve programming skills
Based on an internet research the following websites will serve as a starting point for this very ambitious target :-)

- [Exercism](http://exercism.io/) download and solve practice problems in over 30 different languages. For Python there are 88 exercises available at the time. *Is asking for contribution*
- [CheckIo](https://checkio.org/) coding game where you can improve your coding skills by other users solutions.  
- [Enki](https://www.enki.com/) the 5-minute daily workout for your dev skills. An app which I downloaded to my iPad. My daily dose of python while commuting. *Is asking for contribution*  
- [PEP 20 (The Zen of Python) by example](http://www.artifex.org/~hblanks/talks/2011/pep20_by_example.pdf). Very informative, helpful to understand what actually is meant by the various *zen statements*


### Lessons learned:

- Small exercises such as in [Exercism](http://exercism.io/) allow it to focus on one particular concept, such as for instance try/except/finally or a specific Python built-in class etc. Even though it needs a lot of patience to go through these exercises and no fancy application is the outcome of such exercises, it is absolutely worth it to be patient and focus on one topic at the time
- get used to PEP8   
- understand the differences of mutable and immutable types and also what possible advantages immutable types might have: e.g. no concurrency issues, no side effect issues   
- definition of a return statement instead of a return value only (where useful), this was thanks to code reviews provided to me on [Exercism](http://exercism.io/) by other users.      
- try/except/finally, do not accept an empty except, always specify the error which shall be caught.   


### Conclusion:

- **focus on one language at the time**. I was so eager to improve java, javascript, python and HTML5 all at the same time. This was definitely too much in parallel. Focus on one topic. 
- **it needs a lot of patience**. Coding can be very frustrating, first before the code does what I want it to do, second there are so many options for improvements that it seems to be a never ending story.  