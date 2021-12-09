## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

  -Ansible

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- What aspect of security do load balancers protect? What is the advantage of a jump box?_The load balancers protect against any one machine being overloaded. It spreads the incoming network traffic. The jump box creates a portal to restrict the access for engineers to the system.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- What does Filebeat watch for?_Log files
- What does Metricbeat record?_Logs internal files that have recently been changed.

The configuration details of each machine may be found below.
Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address    | Operating System |
|----------|----------|---------------|------------------|
| Jump Box | Gateway  | 10.0.0.1      | Linux            |
| Web-1    | server   | 10.0.0.4      | Linux            |
| Web-2    | server   | 10.0.0.5      | Linux            |
| ELK      | ELK stack| 168.61.166.199| Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 73.65.239.100

Machines within the network can only be accessed by ssh.
- Which machine did you allow to access your ELK VM? What was its IP address? My home machine. 73.65.239.100

A summary of the access policies in place can be found in the table below.

| Name      | Publicly Accessible | Allowed IP Addresses |
|-----------|---------------------|----------------------|
| Jump Box  | Yes                 | 73.65.239.100        |
| Web-1     | No                  | 10.0.0.5             |
| Web-2     | No                  | 10.0.0.6             |
| ELK stack | Yes                 | 168.61.166.199       |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible?_It allows for automation across multiple web servers. Instead of having to configure all of the same settings on all of my different servers.

The playbook implements the following tasks:
- You have to install docker
- You have to install ansible to configure your machines
- You then have to attach ansible to your webservers and your elkstack
- You can then run .yml scripts to configure the connection to your elkstack from your webservers.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Update the path with the name of your screenshot of docker ps output](Images/docker ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5, and 10.0.0.4.

We have installed the following Beats on these machines:
- Filesbeats, and metricbeats

These Beats allow us to collect the following information from each machine:
- Filebeats tracks log data and works on forwarding it to the ELK stack for easier monitoring. Metricbeats collects the statistics from the servers and sends them to the ELK stack for a good centralized monitoring source.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the public SSH key from the ansible machine to the destination server.
- Update the hosts file to include the IP addresses of the specific machines you want affected by the .yml playbook.
- Run the playbook, and navigate to 168.61.166.199(ELK server machine) to check that the installation worked as expected.


