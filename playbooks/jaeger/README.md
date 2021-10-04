Ansible environment setup:
==========================

ssh 10.9.28.53
python3 -m virtualenv ansible
source ~/ansible/bin/activate
python3 -m pip3 install six netaddr requests google-auth
git clone git@github.com:carousell/ctf-platform-ansible.git
cd ctf-platform-ansible
git submodule update --init --recursive
--------------------------------------------------------------------------------------------------

Update Inventory File:
======================
[all:vars]
ansible_connection=ssh
ansible_become_method=sudo
ansible_become=true
auth_kind=serviceaccount
service_account_email=<GCP Service Account which has owner permission on the target GCP project>
service_account_file=<Credential file in json format for the service account specified>
project=<GCP Project Name>
  
[Hosts]
IP_ADDRESS or FQDN which is applicable
---------------------------------------------------------------------------------------------------  
  
Update Playbook File:
=====================
1. Update IP address accordingly
2. Update heapsize as per recommendation
