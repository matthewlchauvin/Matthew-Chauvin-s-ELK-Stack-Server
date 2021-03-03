# Matthew-Chauvin-s-ELK-Stack-Server
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://github.com/matthewlchauvin/Matthew-Chauvin-s-ELK-Stack-Server/blob/main/diagrams%20%26%20screenshots/Matthew%20Chauvin's%20Cloud%20Server.jpg

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

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

Only the ELK Server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
72.199.137.44

Machines within the network can only be accessed by machines on my home network.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 72.199.137.44        |
| DVWA-VM1 | No                  | 10.0.0.4             |
| DVWA-VM2 | No                  | 10.0.0.4             |
| ELKserver| No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows the process to easily be repeated when setting up anothernetwork.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/matthewlchauvin/Matthew-Chauvin-s-ELK-Stack-Server/blob/main/diagrams%20%26%20screenshots/Screenshot%20(40).png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web 1 &2 VMs

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?
