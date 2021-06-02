The files in this repository were used to configure the network depicted below.
![Azure_RedTeam_resource_group](https://user-images.githubusercontent.com/77369142/120471172-f671c180-c3d6-11eb-960c-c576ef53a360.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/Dean-Bosman/ELK-Stack-Project.git

This document contains the following details:

Description of the Topologu
Access Policies
ELK Configuration

Beats in Use
Machines Being Monitored


How to Use the Ansible Build


Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly Responsive, in addition to restricting overload to the network.

Load blncing mkes sure thr application will be extremely responsive and also restrics overloading the network.having the jump box prevents machines in the network beign exposed in the public domain.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.

Filebeat watches for log files, collects them, and forwards them to Elasticsearch or Logstash.
Metricbeat records metric data from your system and services. Such as CPU usage, memory etc.

The configuration details of each machine may be found below.



| Name       	| Function   	| IP address 	| Operating System 	|
|------------	|------------	|------------	|------------------	|
| Jump Box   	| Gateway    	| 10.0.0.4   	| Linux            	|
| Web-1      	| Web Server 	| 10.0.0.5   	| Linux            	|
| Web-2      	| Web Server 	| 10.0.0.6   	| Linux            	|
| Web-3      	| Web Server 	| 10.0.0.8   	| Linux            	|
| ELK-Server 	| ELK Stack  	| 10.1.0.4   	| Linux            	|







Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump-Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

Personal IP address

Machines within the network can only be accessed by SSH.

Which machine did you allow to access your ELK VM? My Personal public IP

A summary of the access policies in place can be found in the table below.


| Name       	| Publicly Accessable 	| Allowed IP addresses 	|
|------------	|---------------------	|----------------------	|
| Jump Box   	| No                  	| 10.0.0.4             	|
| Web-1      	| No                  	| 10.0.0.5             	|
| Web-2      	| No                  	| 10.0.0.6             	|
| Web-3      	| No                  	| 10.0.0.8             	|
| ELK-Server 	| No                  	| 10.1.0.4             	|













Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

its a quick and easy set up.

The playbook implements the following tasks:

Install Docker
Install python3-pip
Install Docker module pip
Use systemctl to use more memory
Download and launch Docker container sebp/elk:761

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
![ELK sebp elk761](https://user-images.githubusercontent.com/77369142/120470855-9e3abf80-c3d6-11eb-807b-abd2e7a32a75.JPG)


Target Machines & Beats
This ELK server is configured to monitor the following machines:

Web-1, 10.0.0.5
Web-2, 10.0.0.6
Web-3, 10.0.0.8

We have installed the following Beats on these machines:

Filebeat
Metricbeat

These Beats allow us to collect the following information from each machine:

Filebeat collects system logs, which can be used to track system events, etc.
Metricbeat collects system and service metric data, which we can use to see CPU usage, etc.

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the roles_ file to /etc/ansible/roles.
Update the Hosts file to include Webservers IP's and ELK Server IP
Run the playbook, and navigate to http://[ELK-server-IP]:5601/app/kibana to check that the installation worked as expected.

/etc/ansible/roles/filebeat-playbook.yml is the filebeat playbook. Copy it to /etc/ansible/[your_dir]/[your-playbook-name]

/etc/ansible/files/metricbeat-playbook.yml is the metricbeat playbook. Copy it to /etc/ansible/[your_dir]/[your-playbook-name]

update the /etc/ansible/hosts file. '[webservers]' and '[elk]' need to be updated with the IP of the web servers you want to run the playbooks on

