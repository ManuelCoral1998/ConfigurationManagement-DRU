## In this branch (ansible-dynamic-inventory)

We are going to find the changes necessary to use the Dynamic Inventory.

1. Is necessary to have Ansible Server.
2. Is necessary to either export AWS Credentials or install aws cli and configure this information.
3. Is necessary to download following files.
    - ec2.py - This file would be the inventory that you are goint to use, is in charge of get all instances in the region(s)
    - ece.ini

4. Give executing permissions to ec2.py  
        chmod 755 ec2.py

5. Test the script  
        ./ec2.py --list

    #### NOTE (in case this command failds check if you have installed boto - pip install boto)

6. Execute your ansible playbook  
    sudo ansible-playbook -i ec2.py (DIR_TO_YOUT_MAIN_PLAYBOOK) --private-key=(YOUR_PRIVATE_KEY) -u (USER) -vvv -e (ANY_EXTRA_VARS_YOU_NEED)

## Changes  

In the *.yml is necessary to change hosts (target)  

## Extra

1. Ansible to provision two machines/instances using regular variables, extra variables and setting environment vars.

[Using Variables — Ansible Documentation](https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html)

[And setting environment variables in stages](https://docs.ansible.com/ansible/latest/user_guide/playbooks_environment.html)