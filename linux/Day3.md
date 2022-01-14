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
