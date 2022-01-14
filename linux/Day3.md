# iptables
sol -iptables is a command line interface used to set up and maintain tables for the Netfilter firewall for IPv4, included in the Linux kernel. 
The firewall matches packets with rules defined in these tables and then takes the specified action on a possible match.
## There are 5 tables mainly but 3 tables are important
## Filter table - which is default table used for filtering packets . 
## nat : Related to Network Address Translation. It includes PREROUTING and POSTROUTING chains.
## mangle : For specialised packet alteration. Inbuilt chains include PREROUTING and OUTPUT.
### It has 3 chains 
#### INPUT  : set of rules for packets destined to localhost sockets.
#### FORWARD :for packets routed through the device.
#### OUTPUT : for locally generated packets, meant to be transmitted outside.

# Difference between FLUSH and DELETE in iptables.
sol - Flush removes all the rule in iptables from all chains. we can also use flush to remove rules from partical chains
   ## syntax
   ## iptables -F (-F STAND FOR FLUSH)
   ## TO Remove from particular chain
   ## iptables -F (chain name )
# How many types of processes are there in linux  ?
   Types of Processes
   Parent and Child process : The 2nd and 3rd column of the ps –f command shows process id and parent’s process id number. For each user process, there’s a parent      process in the system, with most of the commands having shell as their parent.
   Zombie and Orphan process : After completing its execution a child process is terminated or killed and SIGCHLD updates the parent process about the termination      and thus can continue the task assigned to it. But at times when the parent process is killed before the termination of the child process, the child processes      become orphan processes, with the parent of all processes “init” process, becomes their new pid. 
   A process which is killed but still shows its entry in the process status or the process table is called a zombie process, they are dead and are not used.
   Daemon process : They are system-related background processes that often run with the permissions of root and services requests from other processes, they most      of the time run in the background and wait for processes it can work along with for ex print daemon. 
   When ps –ef is executed, the process with ? in the tty field are daemon processes.
      ref : https://www.geeksforgeeks.org/processes-in-linuxunix/

# How to create symbolic links ?
  sol-> ln is a command-line utility for creating links between files. By default, the ln command creates hard links. To create a symbolic link,
  use the -s (--symbolic) option.
 ###### syntax :ln -s source_file symbolic_link
