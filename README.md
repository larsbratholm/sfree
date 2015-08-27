# sfree
This script, for the slurm queue-system, tries to detect jobs that results in resources being badly utilizes, e.g. if the submit script and program settings doesn't match by mistake.

For all partitions the user has access to, cpu load on all nodes are compared with the number of allocated cpus. Jobs that results in cpus not being able to be used on a node is displayed as well.

Lastly the amount of jobs able to run on 1, 2, 4, 8, 12, 16 and 24 cpus are displayed for each partition. This output is reduced to e.g. 1, 2 and 4 depending on the width of the terminal running the script.

If the user has access to partitions on multiple accounts, just a single account can be analyzed by running "./sfree \<account\_name\>"

Example output:
```
Possible bad CPU utilization:
kemi4 node037    Allocated CPUs: 8     CPU load:  1.0
      User: user1        job-id: 1611400   job-name: pcNmp2OH_nmr
Misuse of memory:
kemi4 node031       6 CPUs blocked by:
      User: user2        job-id: 1611176   Allocated memory:  32768   Allocated CPUs:  2
      User: user2        job-id: 1593925   Allocated memory:  32768   Allocated CPUs:  2
      User: user2        job-id: 1592114   Allocated memory:  32768   Allocated CPUs:  2

Possible submissions:
kemi3:  24 jobs on 1 thread,  12 jobs on 2 threads,   6 jobs on 4 threads
kemi1:  12 jobs on 1 thread,   6 jobs on 2 threads,   3 jobs on 4 threads
kemi4:  10 jobs on 1 thread,   5 jobs on 2 threads,   2 jobs on 4 threads
```
