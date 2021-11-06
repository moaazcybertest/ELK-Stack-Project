# ELK-Stack-Project

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

<img src="https://github.com/v3tro5426/ELK-Stack-Project-1/blob/master/Diagrams/ElkStackDiagram.png" 
     width="700" 
     height="700" />

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

  - ELK-Stack-Project-1/Ansible/

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available for customers, in addition to restricting attacks to the network.
-The advantage of using a jump box is that only the jump box can access the Virtual networks via; ssh.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- Filebeat monitors the log files or locations specified, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- Metricbeat is an extremely easy-to-use, efficient and reliable metric shipper for monitoring your system and the processes running on it. The configuration details of each machine may be found below.

The configuration details of each machine may be found below.
| Name      | Function | IP Address | Operating System |
|-----------|----------|------------|------------------|
| Jump Box  | Gateway  | 10.1.0.4   | Linux            |
| Web-1     | Function | 10.1.0.5   | Linux            |
| Web-2     | Function | 10.1.0.6   | Linux            |
| Web-3     | Function | 10.1.0.7   | Linux            |
| Elk-Server|Monitoring| 10.2.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 5061 Kibana Port

Machines within the network can only be accessed by Jump-Box-Provisioner.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 92.254.14.21         |
|  Web-1   | No                  | 10.1.0.4             |
|  Web-2   | No                  | 10.1.0.4             |
|  Web-3   | No                  | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it saves time and was simple and can overlook vulnerabilities easily.
- To help implement the playbook file

The playbook implements the following tasks:

- Install docker.io
- Install python3-pip
- Install docker via pip
- Increase vitual memory
- Use more memory
- Download and launch a docker elk container 
- Starts docker and establishes the ports being used.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![](https://github.com/v3tro5426/ELK-Stack-Project-1/blob/master/Diagrams/ELK%20docker%20SC.JPG)
     
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 (10.1.0.5)
- Web-2 (10.1.0.6)
- Web-3 (10.1.0.7)

We have installed the following Beats on these machines:
- Filebeat and Metricbeat

- Web-1	10.1.0.5
- Web-2	10.1.0.6
- Web-3	10.1.0.7
- ELK-Server	20.80.194.10

These Beats allow us to collect the following information from each machine:
- These Beats allow us to collect the following information from each machine: 
- Filebeat collects log data and shows them in the monitoring clusters. 
- Metricbeat collects metrics and statistics and shows them in the output specified, for example Elasticsearch or Logstash.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook(.yml) file to Ansible directory.
- Update the host file to include webserver and ELK.
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.(20.80.194.10:5601/app/kibana)
