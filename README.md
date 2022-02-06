# pihole ansible playbook

[![lint](https://github.com/kdpuvvadi/pihole-ansible/actions/workflows/ci.yml/badge.svg)](https://github.com/kdpuvvadi/pihole-ansible/actions/workflows/ci.yml)

## Setup Ansible

* Install pip `sudo apt install python3-pip -y`
* install ansible with pip `pip install ansible`

## Run

* Clone the repo  `git clone https://github.com/kdpuvvadi/pihole-ansible.git pihole-ansible`.
* Install requirements `ansible-galaxy collection install -r requirements.yml`.
* copy `inventory.ini.j2` to `inventory.ini`.
* Change necessary changes to inventory.
* copy `vars.yml.j2` to `vars.yml`.
* Change the variable based on your preferences.

## Run the playbook

* Run `ansible-playbook main.yml` append `-K`
* if you need password for `sudo` for root access on your host. `ansible-playbook main.yml -K`

## Login

After installation, run `docker logs pihole | grep random` to view the password for login and change the password of you choice.

## Ports

Pi-hole uses following ports to work proeprly. Make sure to open the ports inside your network to work properly. 

* 53 - tcp/udp (DNS)
* 90/9943 - tcp (web interface)
