# README
A repository with Ansible playbooks to help install specific cloud tools.
Selected OS: Debian 12

## Appendix
### Install Ansible on Debian 11
```
apt-get update
apt-get install -y python3-pip

pip3 install --upgrade pip

pip install --upgrade ansible
ansible-galaxy collection install --timeout 180 community.general
```
