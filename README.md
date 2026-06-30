In task 1 of the assignement we check the IP address of the GUVI.in using the nslookup which is resolves successfully.
Then We have task to check the cpu and memory usage of my server so we use the command: lscpu and df -h (for the disk space) and 
To check the memory usage i use "free -m".
Then we have to check the connectivity betweeen the 2 nodes so we can check it using the ping command from one node to another one  which is successful in my case.
In task 2 of assignment one file below are my findings:
- Firstly we check the connectivity using the command "nslookup guvi.com" and this confirms the domain resolves to an IP address.
- Secondly we check the connectivity for the port 9000 using the command "nc -zv guvi.com 9000" which is giving teh output "**TIMEOUT**".
- Then we try to run the same command and on the place of 'guvi.com' we try to add our nodes 'public ip' and it is also showing 'timeout'.
- We are getting this "**TIMEOUT**" output that means the port is blocked or it is not exposed.
- We check the same on other ports as well liek "80/443" on these ports it is running successfully.
- Then we run the command "curl -v http://guvi.com:9000" it resolves the dns successfully but for ipv6 it is unreachable because of my EC2 instance.
- As per the output in the screenshot my observation is
  - "Using curl -v, I verified that guvi.com resolves correctly, but connection to port 9000 fails with timeout.
  - This indicates that the port is not open or not publicly exposed.
  - Since there is no connection refused, the service is likely not listening on a public interface or is blocked by firewall/load balancer rules.”
- Then we run the "traceroute guvi.com" which is showing the routes
- We run lastly the "sudo traceroute -T -p 9000 guvi.com" command to check the routes.
- The Final conclusion is "I verified port 9000 using nc -zv, and a timeout indicates the port is not open or not reachable from the network."
- Let me know if anything is wrong or Do i need to learn more on this.
- I would really appreciate your feedback.
