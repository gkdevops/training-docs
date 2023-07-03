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
