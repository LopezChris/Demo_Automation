# Computer Engineering

Containerized Web Application on AWS EC2

## Provision AWS EC2 VM with Ansible

## Step 1: Prep your machine

- Have your security credentials ready to authenticate your AWS Account.

- Set up AWS credentials as environment variables. The playbook needs these at runtime.

~~~bash
export AWS_ACCESS_KEY_ID=<enter your access key>
export AWS_SECRET_ACCESS_KEY=<enter your secret key>
chmod 400 $HOME/.ssh/keypair.pem
export AWS_SSH_KEYPAIR=<enter your keypair path>
~~~

Create a shell script with the above commands and your iam aws credentials, then execute:

~~~bash
source $HOME/.ssh/iam_aws_credentials_env.sh
source $HOME/.ssh/aws_keypair_env.sh
~~~

- Install Ansible based on OS of machine from which you plan to execute the script.

## Step 2: Prepare Ansible playbook

~~~
├── ansible.cfg
├── inventory
│   ├── base
│   ├── ec2.ini
│   ├── ec2.py
│   ├── static_hosts
├── variables.yml
├── ec2_prov_playbook.yml
├── ec2_term_playbook.yml
~~~

- **ansible.cfg** holds configuration info

- **inventory** has the inventory of artifacts

- **variables.yml** has the variables that are used to replace wildcards in your playbooks to make them more reusable

- **ec2_prov_playbook.yml** is the playbook which has a list of tasks to provision an EC2 instance

- **ec2_term_playbook.yml** is the playbook which has a list of tasks to terminate an EC2 instance

## Step 3: Run your playbook

Launch EC2 instance(s)

~~~
cd $HOME/Documents/GitHub/Computer-Engineering/ansible
ansible-playbook -v ec2_prov_playbook.yml
~~~

Terminate EC2 instance(s)

~~~
cd $HOME/Documents/GitHub/Computer-Engineering/ansible
ansible-playbook -v ec2_term_playbook.yml
~~~

## Further Reading

- AWS EC2
- Ansible overview
- Ansible aws_ec2 module
- Regions and Availability Zones

## Setup App

~~~
# Create a React App
npx create-react-app client
cd client
npm start
~~~

~~~
# Create a Express App
mkdir myapp
cd myapp
npm init
npm install express --save
~~~