# This is NOT working for latest edumeet (> v4.X) - only for edumeet 3.X !!!
Help to make this working with latest edumeet is highly appreciated!

# Ansible for edumeet/edumeet-docker install

Basic ansible script to instal eduMeet in docker based on an openstack base debian image.

[![asciicast](https://asciinema.org/a/311365.svg)](https://asciinema.org/a/311365)

## Requirments

You need to have:

* debian/ubuntu base image installed
* global IPv4 address
* dns A record for the ipv4 address
* setup ssh server with sudo

## Prepare for install, config

### Configure vars (dns and ipv4 email turn, etc)

Edit hosts to set host or hosts
Edit group_vars/edumeet.yml
Rename according your hosts, and Edit host_vars/meet.yml

#### TURN

If you are working for the Education or Research community,
then please visit to [https://turn.geant.org)](https://turn.geant.org)
 to get a turn password credential,
 and edit file group_vars/edumeet.yml accordingly.
Otherwise install and configure a turn server (e.g. [https://coturn.net](https://coturn.net))

### Advanced options

For more advanced options see group_vars/all.yml

## Install

### Install ansible external roles

```bash
ansible-galaxy install -r requirements.yml
```

### Run setup playbook

```bash
ansible-playbook -i hosts -u debian playbook.yml
```

### Warning
This playbook uses ferm as firewall so it might break existing configurations with different firewalls on host (like ufw)!!!
