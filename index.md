## About Me
Hello, I'm Arushi Rai a first year Computer Science and Electrical Engineering student at Illinois Tech.

## Project

Learning and Exploring Cobalt -- the HPC Job Management Suite

## Weekly Updates

### Week One
  I spent this week getting familiar with Cobalt's administrative and user commands. I have almost finished installing the simulation environment on a CentOS 6.4 VM based on VirtualBox. Alongside reading about the Cobalt platform, I read the following paper: [Fault-Aware, Utility-Based Job Scheduling on Blue Gene/P systems](http://www.cs.iit.edu/~iraicu/teaching/CS550-S11/cluster09_wtang.pdf). I learned about the various utlitily functions that can optimize the job selection process, as well as the performances gains from fault-aware job allocation. I found it interesting that the basic FCFS beats all of the proposed smart utility functions when it comes to large, time consuming jobs. However, the real efficiency that is derived from smart utility functions is by cutting down the average response rate for shorter jobs. This paper also explored QSim and Blue Gene systems briefly which helped my understanding of how the elements depend on each other. 


### Week Two
This week I had read three papers: Utilization and Predictability in Scheduling in the IBM SP2 with Backfilling (TPDS 61), Improving Batch Scheduling on Blue Gene/Q by relaxing 5D Torus Network Allocation Constraints (IPDPS 15), and Experience and Practice of Batch Scheduling on Leadership Supercomputers at Argonne. The main focus of this week was exploring scheduling techniques and finally knowing the scheduling policy in use at Argonne. 

The first paper, TPDS 61 was published over 20 years ago and aims to create a more stable and predictable scheduling system through conservative backfilling. It argues that agressive (EASY) backfilling does not improve predictability because jobs behind the first job can hypothetically have an indefinite wait-time. When a running job terminates earlier than expected, you retain the originl schedule but compress it. **This point is important because a combination or a form of this method could be used with the dragonfly network where the estimated run time is highly unpredicatable.** 

The second paper, IPDPS 15 describes a couple of allocation mechanisms to externally allocate network resources to applications: MeshSched and CFCA (Contention-free and communication aware.


I have also been exploring the Cobalt code base and alongside reading the code I am refreshing and adding to my knowledge of Python.

The final paper explores some challenges that are present moving forward in Argonne:

1. For some data collection instruments, having on demand computation capabilities would be helpful. 
	Explore task-switching/time-sharing techniques to satisfy this immediate demand.
2. How to prepare the parallel machines at Argonne to deal with queue depth of millions, because of pushes by the government for  HTC workload support.



