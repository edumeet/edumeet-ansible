
#  Basic ansible script to instal Multiparty-Meeting in docker form openstack base debian image.

## Install ansible roles
```
ansible-galaxy install -r requirements.yml
```
## Run setup playbook
ansible-playbook -i hosts -b -u debian setup.yml
