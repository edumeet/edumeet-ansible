
# Ansible for multipartymeeting/mm install

Basic ansible script to instal Multiparty-Meeting in docker based on an openstack base debian image.

### Requirments
You need to have:
* debian/ubuntu base image installed
* global IPv4 address
* dns A record for the ipv4 address
* setup ssh server with sudo

## Prepare for install, config

#### Configure vars (dns and ipv4 email turn, etc)
Edit hosts to set ip 
Edit group_vars/mm.yml

##### TURN

If you are working for the Education or Research community, 
then please visit to https://turn.geant.org
 to get a turn password credential,
 and edit file group_vars/mm.yml accordingly.
Otherwise install and configure a turn server (e.g. https://coturn.net)

#### Advanced options
For more advanced options see group_vars/all.yml

## Install

### Install ansible external roles

```bash
ansible-galaxy install -r requirements.yml
```

### Run setup playbook

```bash
ansible-playbook -i hosts -b -u debian playbook.yml
```
