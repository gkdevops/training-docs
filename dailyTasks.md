## Tasks

---------------------
What is API

What is Rest API

What protocol it uses

How is Rest API used

Install AWS CLI on Windows

Create a EC2 Instance with user-data to install Java 11

Configure AWS CLI using credentils with default profile

Create a EC2 Instance using AWS CLI with Amazon Linux 2 AMI

---------------------
Install the jq command

Learn the jq command examples using AWS CLI output to query different values

Create a EBS Volume

Attach a EBS Volume using AWS CLI

Mount the Volume to EC2 Instance

Create a snapshot from EBS Volume

Create a snapshot policy from EBS Volume

Create a Volume from Snapshot

---------------------
Create a VPC with dns enabled with 172.31.0.0/16 CIDR range

Create 2 Public Subnet with /24 CIDR range

Create 2 Private Subnet with /24 CIDR range

Create a Public and Private Route Tables and associate the public and private subnets to route tables accordingly

Create a Internet Gateway and attach to VPC

Add a route for IGW in Public Route table with 0.0.0.0/0 source

Create a Nat Gateway associated to a Public Subnet and Elastic IP

Add a route for NGW in Private Route table with 0.0.0.0/0 source

Read about Layer 4 and Layer 7 networks further

------------------------

AWS RDS CLI Tools to install to test the RDS connectivity

Install Java 11 using below link
https://www.oracle.com/java/technologies/downloads/#java11

Install Oracle Basic Client and SQLPlus addon from below link
https://www.oracle.com/database/technologies/instant-client/linux-x86-64-downloads.html

RDS Tutorial
https://aws.amazon.com/getting-started/hands-on/create-oracle-se2-instance-in-multi-az-deployment-on-amazon-rds/

RDS Connectivity Errors
https://repost.aws/knowledge-center/rds-oracle-connection-errors

AWS RePost for AWS provided solutions
https://repost.aws/

------------------------

Understand what is checksum for a file and what are the usescases

Learn md5sum, sha256sum commands

Write a shell script to compare 2 files using their checksum

------------------------

GIT:
https://git-scm.com/

Agile Project:

1 copy of code

Sprint: 15 to 21 typically, where dev team will write the code and test and finally on last day we deploy the code to Production

new code for a business req

during this time there is a production issue, live code has a issue
Now, we will fix the live issue and add code to github and deploy

if we already added some new code to github for new feature, this will be 

1. Revert back all code changes part of new sprint
   then add Prod fix and deploy code

There are 2 different features being built
2 dev, each working on different feature

2 features, 1 is short term: 145 days
long term feature: 

Of creating multiple branches and each branch will have it own version history from its parent then its own history later.

-----------------------------


Build Script: pom.xml ( Maven build script )

<dependency>
    <groupId>org.apache.pdfbox</groupId>
    <artifactId>pdfbox</artifactId>
    <version>2.0.28</version>
</dependency>

mvn Default Lifecycle:

Compile: mvn compile
1. Download all dependency 3rd party packages for main directory code
2. Compiles all Java code under main directory
   .class files for all the code in main directory

Test Compile: mvn test-compile
1. Download all dependency 3rd party packages of test directory code
2. Compiles all Java code under test directory

Only Unit Test cases are written in the test directory

Test: mvn test
1. It will execute the Unit test cases and provide the results

Package: mvn package
We have 10's to 100's of .class files, these files can't be easily managed. Either during deployment, running code, copying code
1. It will package all the code into a single file

   .jar //Modern microservcies spring,springboot: java archive
   .war //have some UI code, with ejb,struts, hibernate. web archive
   .ear // enterprise archive: it can have multiple wars + jars

Final Goal: a single file, which we take and deploy to servers.
----
Maven CLean Lifecycle:
There a lot of junk/unneceassary files generated during build process
those all will be deleted.

mvn clean

---------------------

Java Install in Amazon Linux: https://cloudkatha.com/how-to-install-openjdk-11-on-amazon-linux-2/

Assignment: https://github.com/gkdevops/PetClinic

---------------------

Webservers
App Servers
Database Servers

We have alteast 4 environments: all servers will be 4 sets
Prod we will have many, dev we will 1 or 2 for each application

We will have a lot of app servers

We install, setup, configure, deploy and patch Operating Systems.
ensuring to maintain the exact configuration continously on all servers.

on hundereds on machines:

shell scripts are being written for a very long time:
bash scripting: This a set of linux commands written in a file.
bash scripts are hard to understand, troubleshoot and debug.
logging is not mature.

python: not everyone can write.

Configuration Management Tools: are category of tools which help to automate Linux/windows or manage Operating System configurations.

Puppet -> Ruby
Chef ->
Ansible -> 
Salt Stack ->

Installing Apache
Installing Tomcat
Creating Users
Crearting groups
mouting storage

ensuring all the same configration is applied to all resources of same category.

petclinic.war needs to be deployed to 5 servers

stop existing version of code
clear/delete old code
copy new code
if any config changes of tomcat
start application
do a small health check

dev,sit,uat and prod

installed tomcat
setup all configuration of tomcat
deployed code

It should be ensured to be matched 24x7
kernel properties, os properties, tomcat properties, docker proeprties

Ansible code is written in YAML syntax
syntax is just to define a configuration:

100 lines of ansible code using YAML
it executes from line 1 to 100

Agent and Server concept is very popular and used very often to manage distributed systems.

monitoring tools:
CEntral Server: which will collect all the data from all servers
ALl servers: will have a agent installed, which collect data and send to Central Server.

Agentless:
No need of special ports and no need of any ssl certs:
Chef and Puppet: special port opened and ssl certs were needed

Ansible: doesn't need any special port opened:
openSSH: secure by default: SSH connection to a server

SSH Keys for securing remote access to servers.

Ansible Controller Node: The server where we install Ansible Tool
Remote Nodes: 

Pre-requisite tool: Python is mandatory for ansible to run.
We can't even install ansible without python

Python is mandatory on all remote machines

user management in linux:

creation of user
lock/unlock a user
delete user
update a user
add to groups

Module is a python program written by ansible team to perform all the known possible activites of the user management/system task.

to call this module and provide our inputs/ fill in the blanks.

3000's modules:
Each module target one specific system activity

package mangement
time/date
user
group
stop/start services
kernel properties
networking
change hostname

Networking Modules:
Cisco: addNetwork

package:
install, upgrade, uninstall a package

yum:
  name: httpd
  state: latest

We can write our own custom module:

name: Install nginx
yum:
  name: nginx
  state: installed

template:
  src: /opt
  dest: /opt/

service:
  name: nginx
  state: restarted

Ansible will convert this YAML to python code by filling data and then it will copy this python code to remote nodes
then it will execute the python code which is copied in remote nodes

server by server
Parallely for all servers. ( we can control max parallel servers)

Ansible Controller: does everything

When u write code, we place the code only in controller machine.

Controller will push the code to remote nodes and execute it.

Chef/Puppet: Code is in Puppet Server

Puppet Agents: Will pull the code from Puppet Server

IaC: store the code in GitHub

-------------------------

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

https://docs.ansible.com/ansible/latest/collections/index.html#list-of-collections

https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html#plugins-in-ansible-builtin

Ansible Community Package version: 8, Ansible Core on 2.15

Install Ansible as root
sudo su -
pip --version
pip3 --version
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py
sudo python3 -m pip install ansible

Execute Ansible: 2 ways

Adhoc Method: ansible ....
Playbook Method: ansible-playbook ...

SSH keys based authentication:
We need to generate ssh keys and share to remote nodes.
not required to do this on remote nodes.

Ansible in AWS:
1. We a discovery script to auto generate the Inventory file
2. You need to ensure to copy the public cert to all new VM's part of user-data

Ping Module:
1. Connect to remote node
2. verify the authentication available
3. Check if python is installed or not

ON Prem inventory is kind of stable or unchanged

Adhoc Command Syntax:

ansible <inventory_group_name> -m <module name> -a <aruguments>
ansible <IP/Hostname> -m <module name> -a <aruguments>

ansible webservers -m yum -a "name=tree state=present"

Ansible:
Legacy applications which are running on VM's ( EC2, VMware )

Microservies, which are running on Docker, Kubernetes

Idompotency:
Before applying the code
It will compare the current state with the desired state
If any deviation, then only it apply code, if not it will take no action

Ensuing the system state doesn't effect by executing over and over

Install,Setup, 1 time config, deploy

Ensuring the state of the system is always as expected
java 1.8.1

-------------------

How do you Plan to write your ansible code for the automation task/request?

understand the requirements
which servers are part of automation for inventory management
OS version of servers
What tools need to be installed, any pre-requsities
What is the goal.


1. Perform all the steps manually to achieve requirement.
2. Once performed manually, we will convert each linux command to a ansible module.
3. testing and finalize

Ansible-Lint: to check and provide code syntax and best practices.
https://ansible.readthedocs.io/projects/lint/usage/

----------------------

Ansible Galaxy: https://galaxy.ansible.com/

Ansible Module:

We may need to automate same activity for different teams, applications, teams with cusomizations

Install, Configure and Setup Nginx:

Customization:
Port number
location of apache config files
install version
apache web server properties: logging level, redirection,
ssl config
certificates location

Tomcat:
Elastic Stack:


1. Write a Ansible Playbook customized for each team and maintain it
   10 teams, we will 10 playbooks and maintain them.

2. Write a common ansible code which is reusable across multiple teams
   Ansible Module
   through variables, we will allow the teams to customize

When the amount of code is increasing to 100's of lines, then using Module


ansible-module
ansible-galaxy

Modules can be shared to others. The web portal where we upload the modules is called Ansible Galaxy

meta: information about the module.

Both used to define variables
Defaults: define the variables which we plan to override
vars: variable which will not be overridden

Best Practice:
All the variables defined part of the Module, needs to start with module name

tasks: To define the tasks required for ansible automation

Files handled part of the Ansible Module:
to copy files from Controller Node to Remote Nodes

copy:
  src: 


Ansible desired state/idompotent:
file: touch
service: restart

Ansible Code: 

service:
  name: httpd
  state: restarted

why restart is needed for applications:
config changes:
code changes:

handlers: Allow conditional execution of ansible tasks.

If there is a change, then only run the task, if not ignore.
based on depdency with other task.

copy:
ok state: success and no change needed. 
changed state: success and change made to make on remote node
Handlers are only triggered when changed state is recieved.

For module, we don't have header section
We need to write a playbook and then call the module from that playbook

--------------------

Docker: Create RHEL or Ubuntu VM
https://docs.docker.com/engine/install/rhel/

Pre-requisites:
sudo yum install -y yum-utils

Package Repo:
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

Install Command:
sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

Post Install:
sudo systemctl status docker
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -a -G docker ec2-user

---------------------

https://docs.docker.com/engine/reference/commandline/dockerd/#description

docker image:
Without docker image, we cannot create a docker container.

We can either create our own customer image
we can also download any existing docker image from Docker Hub ( Docker Registry )

Docker Registry: Any software which will store, allow to upload ( versions ) and download docker images, its called a Docker Registry

Base Images:
Every docker image we create, will have a base image. The OS files

Docker Images:

<Image Name>:<Tag Name>
httpd:

Detached Mode ( background mode )
foreground mode

-----------------------

Dockerfile:
Best Practise: 
Dockerfile should be stored along with source code at the top level directory structure in git
Dockerfile should always be executed from the location is it placed on server.

Hadolint: https://github.com/hadolint/hadolint
To scan Dockerfiles for syntax, security enhancements and best practices for Instructions.

-----------------------

Docker Image creation best practices:

https://sysdig.com/blog/dockerfile-best-practices/
https://blog.aquasec.com/docker-security-best-practices

-----------------------

AWS EBS CSI Driver Implementation in EKS:
https://docs.aws.amazon.com/eks/latest/userguide/ebs-csi.html

-----------------------

Jenkins Introduction:

CI:

Jenkins
Azure DevOps
GitHub Actions:
GitLab CI:

Continous Integration:
To ensure developers are checking in code to VSC each time they change it and we need to ensure that this code needs to be verified each time by compiling, running unit tests and building packages to have confidence that the code works as expected.
If this fails, we notify developers immediately and then they perform the fix without going to next stage.
We also will detect issues between developers also.

Developers check code to Central Code Repository
CI Jobs triggers automatically:

1. Code checkout from Github
2. Compile the code and run unit test cases using maven
3. Scan code using code quality tool like SonarQube (SAST Tool) + Check for issues and fail the build if critical issues found.
4. Scan code using to any 3rd party vulnerabilities imported by code (SCA Tool) Snyk, if critical issues are found, we can stop build.
5. Generate the package using maven ( .jar/.war)
6. Create Docker image using Dockerfile
7. Scan Docker Image (Trivy) & Upload the Docker image to registry

CD:
We deploy the code to approriate environment.

Legacy: Ansible
Stop the app
remove old code
deploy new code
Start the app

Containers: Helm/Kubectl
Update the new image tag
apply the deployment.yaml

Run Functional and UI Testing
Send notification
We will deploy code in Continous Delivery/Deployment

Argo CD:

java -jar jenkins.war

Local user management should never be performed.

-----------------
