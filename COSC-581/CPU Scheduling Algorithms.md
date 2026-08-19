
The CPU can only do one thing at a time, so for many processes to run simultaneously, the CPU scheduler decides whcih process gets the CPU's attention and for how long. 

**Goals**: 
1. Maximize CPU utilization: Keep the CPU as busy as possible
2. Be "Fair": Ensure that no process is stuck waiting
3. Provide fast / smooth response times: freezing is bad lol

Performance Metrics


| Metric                     | Goal     | Description                                                |
| -------------------------- | -------- | ---------------------------------------------------------- |
| CPU Utilization            | Maximize | Keep the CPU at 100% work capacity                         |
| Throughput                 | Maximize | Number of processes completed per unit of time             |
| Turnaround Time (makespan) | Minimize | Total time from submission to completion                   |
| Waiting Time               | Minimize | Amount of time a process spends waiting as "ready"         |
| Response Time              | Minimize | Time from submission until the first response is produced. |

# Algorithms
**Preemptive**: The OS can "kick" a process off the CPU.
**Non-preemptive**: The process stays until it is done. 

## First-Come, First-Served (FCFS)
Uses a simple queue to schedule processes. Whoever arrives at the CPU first gets the resources.
- Pros: Easy to understand and implement
- Cons: The "Convoy effect." if a slow process arrives, all the quick processes get stuck behind it. 

## Shortest Job First (SJF)
The CPU looks at all the available processes and picks the one with the shortest "burst time" (run time)
- Pros: Provides minimal average waiting time
- Cons: It's hard to predict how long a process will take before it runs. 

## Round Robin (RR)
Designed specifically for time-sharing systems. Each process gets a small unit of CPU time (a time quantum), usually 10-100 milliseconds. If it isn't finished, it's moved to the back of the queue. 
- Pros: Good response time and considered "fair"
- Cons: If the quantum is too small, the CPU spends too much time switching between tasks. 

# Algorithms used by modern Systems

## Windows
Windows uses Multilevel Feedback Queue (MLFQ): A hybrid approach of Round Robin and Priority Scheduling. It is a preemptive scheduling technique. 

- There are 32 priority levels for processes. The scheduler picks the highest priority thread to run.
- Any app that is "in the foreground" (focused) gains a boost in priority to boost "response." The longer a process waits, it recieves a boost in priority as not to "starve" processes. 

## Linux
Since kernel 2.6.23, linux has used the "Completely Fair Scheduler." Measures CPU time rather than wall clock time. It uses a Red-Black Tree data structure to keep track of how much time each process has had, and the process with the lease amount of CPU time is always picked next. 
- Completely "fair" algorithm." Each process runs at 1/n speed, where n is the number of processes. 

## MacOS
macOS is built upon the XNU kernel, which is heavily optimized for power efficiency, especially on Apple Silicon. 

- It uses multiple queues based on the "type" of task
	- Highly interactive: high priority (moving mouse, animations)
	- User initiated: Fast response
	- Utility/background: Lower priority (time machine backups)
- Asymmetric Scheduilng: On modern macs, background tasks are sent to slow, "efficent" cores, and heavy interactive tasks are sent to "performance" cores. 

## Connections

- [[CS581 - Lecture 5-17]]
- [[Home]]
- [[1. Instruction Pipelining - Introduction]]
