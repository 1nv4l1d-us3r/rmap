# rmap
python port scanner that scans random ports and targets from specified lists.

# Requirements 
* Scapy module

# How to use?

  -P  To specify ports(csv) or range of ports.  ex: -p 80,443,8080,200-1000.
  
  -s  Performs SYN scan (Requires Root permission)
   
   TCP/CONNECT scan (default)

  -t  To specify number of threads (default=10)

  -T  To specify Connection timeout in seconds (default=5)
  
  -v  Verbose mode (Not suitable for piping)
   
  -o  output filename 

  Usage:  cat targets.txt | rmap -p 80,443,3306
          cat targets.txt | rmap -s -p 80,100-2000 -v -t 50

# How dose it work?

Takes targets via stdin input and ports as command line arguments.

connect to a random port on a random target and deletes the tested entries if all ports on a target are tested.

prints the target and port of successfull connections.

# Note: 
SYN scan requires root pprivileges .
Higher threads tend to cause DNS queries to fail.
Increasing timeout duration and Adding additional nameservers to resolv.conf is reconmended.

DNS and ip errors are logged on .rmap_errors file in current directory everytime the scanner runs, it contains the hostnames which triggered the errors.
