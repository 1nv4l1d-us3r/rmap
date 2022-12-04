# rmap
python port scanner that scans random ports and targets from specified lists.

# How to use?

  -P  To specify ports (only csv allowed) ex: -p 80,443,8080,200-1000.

  -t  To specify number of threads (default=10)

  -T  To specify Connection timeout in seconds (default=5)
   
  -o  output filename 

  Usage: cat targets.txt | rmap -p 80,443,3306

# How dose it work?

Takes targets via stdin input and ports as command line arguments.

connect to a random port on a random target and deletes the tested entries if all ports on a target are tested.

prints the target and port of successfull connections.

# Note: 

This scanner only performs TCP scan , Increase in number of threads can cause DNS resolutions to fail (atleast in my case).
Increasing timeout duration and Adding additional nameservers to resolv.conf is reconmended.

DNS and ip errors are logged on .rmap_errors file in current directory everytime the scanner runs, it contains the hostnames which triggered the errors.
