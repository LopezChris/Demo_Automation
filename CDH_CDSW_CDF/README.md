## Provisioning Cluster with CDSW

- ami-074e2d6769f445be5 # centos7 ami id may need be updated
- m5d.4xlarge 16 CPU Cores, 64GB RAM, 2x300GB (SSD)
- add storage 
    - root volume 1000GB, 3000 IOPS
- security group
    - inbound all traffic on all ports, All, 0 -65665, anywhere, 0.0.0.0/0, ::/0

- g3.8xlarge (for when we are ready)

## Configuration and installation

