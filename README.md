# sfree
This script tries to detect jobs that results in resources being badly utilizes, e.g. if the submit script and program settings doesn't match by mistake.

For all partitions the user has access to, cpu load on all nodes are compared with the number of allocated cpus. Jobs that results in cpus not being able to be used on a node is displayed as well.

Lastly the amount of jobs able to run on 1, 2, 4, 8 and 12 cpus are displayed for each partition.

If the user has access to partitions on multiple accounts, just a single account can be analyzed by running ./sfree \<account\_name\>
