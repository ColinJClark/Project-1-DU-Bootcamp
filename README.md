# Project-1-DU-Bootcamp
A repository of collected material for Project 1 6/23<br />
The following is a description of implementing the requirements for Project 1 concerning deployment and monitoring of an ELK Stack


# ELK Stack Deployment
- The files in the **Ansible Folder** may be used in whole or in part to deploy the ELK stack and configure the network depicted in the Diagrams folder. <br />
- The .yml files may be used selectively to partially install a stack portion, such as only deploying Metricbeat.<br />

# Network Diagram Topology
![alt text](http://url/to/img.png)
- The deployed network is used to exploit an exposed monitored DVWA<br />
- The network is load balanced<br />
- Following are details of each VM listed as NAME:FUNCTION:IP ADDRESS:OS<br />

**JumpBoxProvisioner:Gateway:10.0.0.4:Linux<br />
Web1:DVWA:10.0.0.5:Linux<br />
Web2:DVWA:10.0.0.6:Linux<br />
Web3:DVWA:10.0.0.7:Linux<br />**
# Accessibility
- The Jump Box will accept connections from the internet from personal IP<br />
- Jump Box IP: 40.71.183.117<br />
- All deployed machines are not exposed to the public internet<br />
- Following are details of accessibility of each VM listed as:<br />
NAME:PUBLIC ACCESSIBILITY: ALLOWED IP CONNECTION<br />

**JumpBoxPorvisioner:Yes:Personal IP<br />
Web1:No:40.71.183.117<br />
Web2:No:40.71.183.117<br />
Web3:No:40.71.183.117<br />**

# ELK Server Config
- Ansible is used to configure the ELK stack, eliminating the need to manually configure.<br />
- The automation is replicable on any network<br />
- The following is implemented via use of the .yml playbooks in the **Ansible Folder**<br />
_Install Docker.io<br />
_Install Python Docker Module<br />
_Give increased virtual memory to the ELK Server<br />
_Download and Install the Docker ELK container<br />
_Maintain settings, downloads, and installs over reboods<br />

# Target Machines and Beats

**Web1:10.0.0.5<br />
Web2:10.0.0.6<br />
Web3:10.0.0.7<br />**

- FileBeat and MetricBeat have been installed on the above listed machines<br />
- FileBeat tracks code run in sudo to change system logs, and also tracks login attempts<br />
- MetricBeat tracks system metrics

# Playbook Instructions
After enabling Ansible control point:<br />
- SSH into the control point<br />
- Copy install-elk.yml file to the ansible /etc/ansible file<br />
- Update the hosts file to include an ELK group and include the IP of the ELK server<br />
- Run the playbook and open Kibana for confirmation
