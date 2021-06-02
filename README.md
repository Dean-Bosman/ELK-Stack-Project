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

TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?

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

TODO: Add whitelisted IP addresses

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

TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
...
...

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
![ELK sebp elk761](https://user-images.githubusercontent.com/77369142/120470855-9e3abf80-c3d6-11eb-807b-abd2e7a32a75.JPG)


Target Machines & Beats
This ELK server is configured to monitor the following machines:

TODO: List the IP addresses of the machines you are monitoring

We have installed the following Beats on these machines:

TODO: Specify which Beats you successfully installed

These Beats allow us to collect the following information from each machine:

TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.


Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the _____ file to _____.
Update the _____ file to include...
Run the playbook, and navigate to ____ to check that the installation worked as expected.

TODO: Answer the following questions to fill in the blanks:

Which file is the playbook? Where do you copy it?
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
_Which URL do you navigate to in order to check that the ELK server is running?

As a Bonus, provide the specific commands the user will need to run to download the playbook, update the files, etc.
