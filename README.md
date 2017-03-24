# ansible-rhosp-director
Ansible Playbook to install and configure Red Hat OpenStack Platform 10 director on a pre-provisioned RHEL 7.3 host

# Prerequisites

- Machine with RHEL 7.3 installed
- Public key authentication set for root user
- Red Hat Network user account with Red Hat OpenStack Platform Subscription available

# Instructions

1 Checkout this repository
2 Configure roles/rhosp_director/vars/main.yml to match your environment
3 Create a vaut file at roles/rhosp_director/vars/vault
  ansible-vault create roles/rhosp_director/vars/vault
4 Start RHEL system slotted for RHOSP-d installation
5 Make sure you can ssh to the RHOSP-d machine as root without having to enter a password
6 Run the playbook
  ansible-playbook --ask-vault-pass -i hosts site.yml

# Vault Vars
vault_rhn_user: Red Hat Network Account Username
vault_rhn_pwd: Red Hat Network Account Password
vault_rhn_pool_name: Subscription Manager pool name to attach to
vault_stack_user_pwd: The hashed password to use for the created stack user 
NOTE: use <code>openssl passwd -salt <salt> -1 <plaintext></code> to create the hashed password to enter above
vault_undercloud_admin_pwd: Password to use for the admin account on the RHOSP-d installation


