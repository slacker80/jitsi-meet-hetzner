# jitsi-meet-hetzner
jitsi-meet@hetzner

## prerequisites

Make sure you have ansible >= 2.8 installed
```
pip3 install hcloud --user
```

Create a API Token: https://docs.hetzner.cloud/#overview-getting-started

Make sure you have the name of your ssh-key set in:
```
inventory/group_vars/all.yml
```

## usage for provisoning vm

```
HCLOUD_TOKEN=XXXXXXXXX  ansible-playbook -i inventory/  playbooks/provision-vm.yml
```
