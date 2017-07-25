## About Me
Hello, I'm Arushi Rai a first year Computer Science and Electrical Engineering student at Illinois Tech.

## Project

Qsim related

## Weekly Updates

### Week One
  I spent this week getting familiar with Cobalt's administrative and user commands. I have almost finished installing the simulation environment on a CentOS 6.4 VM based on VirtualBox. Alongside reading about the Cobalt platform, I read the following paper: [Fault-Aware, Utility-Based Job Scheduling on Blue Gene/P systems](http://www.cs.iit.edu/~iraicu/teaching/CS550-S11/cluster09_wtang.pdf). I learned about the various utlitily functions that can optimize the job selection process, as well as the performances gains from fault-aware job allocation. I found it interesting that the basic FCFS beats all of the proposed smart utility functions when it comes to large, time consuming jobs. However, the real efficiency that is derived from smart utility functions is by cutting down the average response rate for shorter jobs. This paper also explored QSim and Blue Gene systems briefly which helped my understanding of how the elements depend on each other. 


### Week Two

This week I had read three papers

- TPDS 61: Utilization and Predictabilit in Scheduling in the IBM SP2 with Backfilling
	- to create a more stable and predictable scheduling system through conservative backfilling. It argues that agressive (EASY) backfilling does not improve predictability because jobs behind the first job can hypothetically have an indefinate wait-time. When a previous jobs terminate earlier than expected, you retain the originl schedule but compress it. This point is important because a combination or a form of this method could be used with the dragonfly network where the estimated run time is highly unpredicatable. 

- IPDPS 15: Improving Batch Scheduling on Blue Gene/Q by relaxing 5D Torus Network Allocation Constraints
	- The purpose of this paper is to figure out ways to externally allocate network resources to applications. MeshSched and CFCA (Contention-free and communication aware)

The last paper puts all of these concepts and the previous one together to show how they all form Cobalt.

This has helped my understand of Cobalt because

I have also been exploring the Cobalt code base
	- understand the

alongside reading the code I am refreshing and adding to my knowledge of Python

I hope to do explore the following idea in the next week:

-
-

this is an area I see room for improvement.
