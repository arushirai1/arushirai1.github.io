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

### Week Three
I read the following papers assigned by Professor Lan.

1) Watch Out for the Bully! Job Interference Study on Dragonfly Network:
This paper studied the effects of random job placement coupled with adaptive routing on individual jobs. It found that less communication intensive applications were being affected negatively. Essentially, the goal is to minimize the worst case of less comunication intensive applications, but keep the performance of communication intensive applications. The method which was tested was a hybrid-random-contiguous-adaptive allocation. The less communication intensive applications would be placed contiguously and the rest would be allocated randomly, load balancing. While this method showed some improvement, the performance of less communication intesive apps are still significantly affected. **This is why minimizing the worst case of less communication intensive applications still remains an important task.**

2) Job Scheduling HPC Clusters:
This report established the two classes of clusters: high throughput computing (HTC) clusters and high performance computing (HPC) clusters. For HTC clusters reducing load imbalance to maximize the number of jobs completed are critical goals, whereas minimizing communication overhead is a consideration that must be taken with any HPC cluster. Essentially because there is active communication taking place between nodes in HPC clusters, communication speed is vital because it directly affects the performance of the application and the time in which the job is completed. This report further details the general architecture of HPC clusters and the various terminologies to explain the metrics and approaches for job scheduling.


Reading these two papers raised some questions on the dragonfly architecture itself and Application Placement Scheduler (ALPS) which is the internal scheduler used on Cray platforms. This led me to read the original paper on the dragonfly topology. This clarified the overall architecture, but I still need to know **how exactly this is applied on the Theta system.** Lastly, I learned that APLS is used to create a level of abstraction between the an external resource management model, like Cobalt, and the underlying hardware and operating system architecture.

I also read the user guide on Theta and MIRA, mainly focusing on the former.

### Week Four
Data center scheduling is done without knowing the duration in advanced, so a hybrid scheduling method that is both suitable for HPC clusters and utilizes the unknown duration-based scheduling components of data center scheduling could help improve scheduling efficiency.
These are the blog article and papers I was assigned this week:
(blog post) The evolution of cluster scheduler architectures:
There are five types of scheduler architectures on **HTC** clusters: monolithic, two-level scheduling (involves partitioning), shared-state architectures, fully distributed architectures, and hybrid architectures which combine fully distributed with monolithic or shared state designs. Essentially using a distributed model for short tasks and low priority batch workloads and using a centralized (monolithic or shared state?) for the rest.

[insert comparison table]

By reading the user guide on Theta, “Early Evaluation of the Cray XC40 Xeon Phi System ‘Theta’ at Argonne, and the “Validation Study of CODES dragonfly network model against Theta ALCF system” I gained a better understanding of the capabilities and limitations of Theta. However, I have not pieced together how I could utilize this in terms of building an appropriate scheduler, this remains a key focus of this following week. Though it has a lot of useful information for when I build an experiment. Because of the level of variability with respect to MPI performance can be significant when there is sudden contention caused by an interfering job, many data points should be run to ensure statistical accuracy. I also thought core specialization was an interesting idea. Also running more than one thread per core, does not improve performance, and degrades performance after two. Lastly, the final paper showed the effect of scale on the benchmark tests and also reached the conclusion that the CODES simulation is largely accurate. However, I noticed that the Bully paper (I read last week) did not have the same configurations as this Theta system, but I guess it doesn’t matter since it just affects latency which I believe is linear.

