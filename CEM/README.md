
install these

AWS IAM Access with minimal access to your instance list and details
EC2 Instances running on top of AWS
Python virtualenv installed on your device

~~~
pip install -r ansible/requirements.txt
~~~

Export ec2.py and ec2.ini as environment variables

~~~
export ANSIBLE_HOSTS=$HOME/Documents/GitHub/Demo_Automation/CEM/ansible/inventory/ec2.py
export EC2_INI_PATH=$HOME/Documents/GitHub/Demo_Automation/CEM/ansible/inventory/ec2.ini
~~~

Add to your ssh agent, your keypair:

~~~
ssh-agent bash
ssh-add ~/.ssh/your-iam-keypair.pem
~~~

Test the ec2.py script works:

~~~
python $HOME/Documents/GitHub/Demo_Automation/CEM/ansible/inventory/ec2.py
~~~

You should receive json output that describes your EC2 instance(s).