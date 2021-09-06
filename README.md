## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project-1.png](https://github.com/sweeder/unit-13/blob/main/Diagram/Project-1.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

![Install-Elk.yml](https://github.com/sweeder/unit-13/blob/main/Ansible/install-elk.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting traffic to the network.

Load balancers protect the connection of the DVWA virtual machines to the internet. The advantage of a jump box is flexibility. In case of a damaged host device, the jump box will always be availabl through the cloud.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.

- Filebeat watches for security data sources that simplify the collection, parsing, and visualization of common log formats.
- Metricbeat records behaviour and usage of system resources.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name           | Function            | IP Address        | Operating System      |
|----------------|---------------------|-------------------|-----------------------|
| Jump Box       | Gateway             | 10.0.0.4          | Linux                 |
| WebVM1         | Webserver           | 10.0.0.6          | Linux                 |
| WebVM2         | webserver           | 10.0.0.7          | Linux                 |
| ELK server     | Kibana host         | 10.2.0.5          | Linux                 |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 10.0.0.162:22

Machines within the network can only be accessed by ssh protocol.
- The jump box machine has acces to ssh into the ELK server. 
    EX: ssh RedAdmin@10.2.0.5

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| WebVM1   |  No                 | 10.0.0.6             |
| WebVM2   |  No                 | 10.0.0.7             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- The advantage of automation is time consumption, ubiquitious settings, and streamline connectivity

The playbook implements the following tasks:
- Step 1: Install docker.io
- Step 2: Install pip3
- Step 3: Increase virtual machine memory
- Step 4: Download and launch ELK ocntainer and enable associated ports
- Step 5: Enable docker on reboots

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Docker ps](https://github.com/sweeder/unit-13/main/docker_ps_output.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Two machines being monitored are: 10.0.0.6 & 10.0.0.7 

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
