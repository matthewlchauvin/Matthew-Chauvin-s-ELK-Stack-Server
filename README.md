# Matthew-Chauvin's-ELK-Stack-Server
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/matthewlchauvin/Matthew-Chauvin-s-ELK-Stack-Server/blob/main/diagrams%20%26%20screenshots/Matthew%20Chauvin's%20Cloud%20Server.jpg

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/matthewlchauvin/Matthew-Chauvin-s-ELK-Stack-Server/tree/main/ansible

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly stable, in addition to restricting access to the network.
The load balancer ensures that the network won't be overwhelmed, helping protect the network from denial of service attacks._

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.


The configuration details of each machine may be found below.

| Name       | Function | IP Address | Operating System |
|------------|----------|------------|------------------|
| Jump Box   | Gateway  | 10.0.0.4   | Linux            |
| Web 1      | Server   | 10.0.0.5   | Linux            |
| Web 2      | Server   | 10.0.0.6   | Linux            |
| ELK Server | Server   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
72.199.137.44

Machines within the network can only be accessed by machines on my home network.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | 72.199.137.44        |
| Web 1    | No                  | 10.0.0.4             |
| Web 2    | No                  | 10.0.0.4             |
| ELKserver| No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows the process to easily be repeated when setting up anothernetwork.

The playbook implements the following tasks:
- Install Docker
- Install python3-pip
- Install Docker python module
- Set the vm.max_map_count to 262144
- Download and launch a docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/matthewlchauvin/Matthew-Chauvin-s-ELK-Stack-Server/blob/main/diagrams%20%26%20screenshots/Screenshot%20(40).png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web 1 &2 VMs

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat monitors the log files or locations that you specify, which we use to see what changes or messages the log files have received such as kill commands. Metricbeat records the metrics and statistics from the operation system and from services running on the server, which we could use to look at how much RAM or CPU usage was being used on the webservers at certain time

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the install-elk.yml and filebeat-playbook.yml file to /etc/ansible
- Update the install-elk.yml and filebeat-playbook.yml file to include the machine you want use the playbooks on by changing the hosts name on the 3rd line
- Run the playbook, and navigate to http://[your.VM.IP]:5601/app/kibana to check that the installation worked as expected
