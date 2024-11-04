EC2-public IP : 13.234.29.81
Site accessible at - http://13.234.29.81:8000

REPORT ON ISSUES IDENTIFIED DURING DEBUGGING- 
-	Mostly spelling/ syntax errors were identified, for example, WORKDIR/appp which should be WORKDIR/app. Other examples include “eight thousand” which should be 8000, “netiface” which should be “netifaces”, etc.(trivial spelling mistakes, mostly) 
-	docker-compose up worked, on IDE, with the inclusion of a port binding in the docker-compose.yaml file which bound the container’s port to the host machine's. 
-	I faced trouble with the permissions regarding the .pem file. A chmod command, specifically, “chmod 400 webserver-01.pem” , which was supposed to convert its permissions to read-only did not work when executed from the WSL terminal. I had to edit permission properties from file explorer and then run the ssh -i command from powershell and that let me access the EC2 terminal. 
-	With the docker-compose up successfully running on the amazon linux 2023 EC2 terminal, I had to edit the inbound access in the ec2 instance properties to include 8000 as a viable port which finally led to the IP working. 
-	The whole process of setting up a directory in ec2-user and finally importing the files from my machine to the virtual machine was very educational, mostly because of configuration issues that weren’t obvious at first.
