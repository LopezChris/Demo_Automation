## Provisioning Cluster with CDSW

Specifications for AWS EC2 instance

- AMI: ami-074e2d6769f445be5

- ami-074e2d6769f445be5 # centos7 ami id may need be updated
- m5d.4xlarge 16 CPU Cores, 64GB RAM, 2x300GB (SSD)
- add storage 
    - update root volume to 100GB OS Disk Space, 300 IOPS
    - add EBS /dev/sde 1000GB SSD 3000 IOPS 
        - for Docker device disk
- security group
    - inbound all traffic on all ports, All, 0 -65665, anywhere, 0.0.0.0/0, ::/0

- g3.8xlarge (for when we are ready)

## Configuration and installation

- ssh into AWS EC2 VM and copy this repo

$ sudo su -
$ yum install -y git
$ git clone https://github.com/fabiog1901/OneNodeCDHCluster.git
$ cd OneNodeCDHCluster
$ chmod +x setup.sh

run `lsblk` to find out what docker device mount is.

Ex command with docker mount:

./setup.sh aws cdsw_template.json /dev/nvme1n1

