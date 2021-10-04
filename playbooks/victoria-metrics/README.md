Ansible environment setup:
==========================
python3 -m virtualenv ansible
source ~/ansible/bin/activate
python3 -m pip3 install six netaddr requests google-auth
cd ansible // Assume you have uploaded your roles and playbooks here
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
