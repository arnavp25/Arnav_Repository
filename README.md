# ELK Stack Deployment
The files have been used to create a working ELK Deployment on Azure. YML files in repository can be used to install it.
  elk.yml
•	Filebeat-config.yml
•	Metricbeat-config.yml
# Topology
The topology depicts the network that has been created using load-balancer and DVWA. Load balancing is to maintain high availability. Security groups are also implemented to control access. The jump box is used to get access to all the VMs through SSH. Including ELK server helps users monitor vulnerable VM.
•	Filebeat watches for events in log files or other specified locations. It forwards these events to either Elasticsearch of Logstash.
•	Metricbeat records metrics and statistics from the system services running on the server. It forwards these to Elasticsearch or Logstash
# IP Table
| Name	  | Type	  | IP Address |
|Jump Box |	Gateway	| 10.0.0.1   |  
|Web1	    |WebServer|	10.0.0.5   |
|Web2	    |WebServer|	10.0.0.7   |
|ELK	    |LogServer|	10.1.0.4   |
|LB	      |Kibana   |	Public IP  | 

# Access Policies
Access policies has been created through security groups which manages and restrict the access towards the webservers. The traffic only goes through load balancer.
Name	Access Allowed	Allowed IP Addresses
Jump Box	Yes	204.11.218.122

NLB	Yes	Internet
Web1	no	NLB IP Addr
Web2	no	NLB IP Addr
Elk	Yes	52.228.119.219

# Usage 
Once all the VM are up and running. SSH to the VM and copy the playbook.yml file to /etc/ansible/. Update the host file , which include the IP required and “ansible_python_interpreter=/usr/bin/pyhton3”.
Run the Playbook, if the screen suggests everything worked as needed, go to http://publicIP:5601/app/kibana to check if it worked



