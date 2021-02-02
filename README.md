# Axelerant
6 Demonstrate the following server monitoring.

1. List the top 5 unique IP addresses accessing your Apache webserver.
2. List the past 10-days 4XX results of Apache's access log file, sorted by date with their IP address.
3. Write a utility script to view the top 10 disk-space users of a given path across multiple hosts.


@ 1. awk '{ print $1}' access.log | sort | uniq -c | sort -nr | head -n 5

@ 2. find . -mtime +10 -w "4XX" -name "access.log" -exec ls  {} \;

@ 3. 

for i in *
do
du -ha /home/ | sort -n -r | head -n 10
done
