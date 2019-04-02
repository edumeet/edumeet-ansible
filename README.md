
# Ansible for mm install

Basic ansible script to instal Multiparty-Meeting in docker based on an openstack base debian image.

## Edit group_var/mm.yml

Go to https://turn.geant.org get a turn password credential, and edit file var/mm.yml accordingly.

## Install ansible roles

```bash
ansible-galaxy install -r requirements.yml
```

## Run setup playbook

```bash
ansible-playbook -i hosts -b -u debian main.yml
```