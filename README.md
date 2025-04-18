# README
A repository with Ansible playbooks to help install a set of tools.
Scripted to run on Debian 12 or Ubuntu 24.04 machines.

## System pre-install script
- Get the OS level packages
- Download this repo and install Docker and other tools

```bash
set -x

## install os packages
sudo apt-get update
sudo apt-get install -y git python3-venv unzip

## setup python venv
if [[ ! -d ~/.venv ]]
then
  mkdir ~/.venv
  python3 -m venv ~/.venv
fi

source ~/.venv/bin/activate
echo 'source ~/.venv/bin/activate' >> ~/.bashrc
pip install ansible

## pull my tools setup repo
git clone https://github.com/tlhakhan/tools.git

## install docker
cd tools
./docker.yaml

## add user to the docker group
sudo usermod -aG docker "$USER"
```
