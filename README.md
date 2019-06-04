
# Ansible for mm install

Basic ansible script to instal Multiparty-Meeting in docker based on an openstack base debian image.

## Edit group_var/mm.yml

Go to https://turn.geant.org get a turn password credential, and edit file var/mm.yml accordingly.

### Login Open ID Connect
In config if you want to use OIDC auth, then please set login to true,
otherwise you can safely skip this login config section.

## Install ansible roles

```bash
ansible-galaxy install -r requirements.yml
```

## Run setup playbook

```bash
ansible-playbook -i hosts -b -u debian main.yml
```
