# rmap
python port scanner that scans random ports and targets from specified lists.

How to use?

  -P  To specify ports ex: -p 80,443,8080.

  -t  To specify number of threads (default=5)

  -T  To specify Connection timeout in seconds (default=3)
   
  -o  output filename 

  Usage: cat targets.txt | rmap -p 80,443,3306

How dose it work?

Takes targets via stdin input and ports as command line arguments.

connect to a random port on a random target and deletes the tested entries if all ports on a target are tested.

prints the target and port of successfull connections.

