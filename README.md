# jitsi-meet-hetzner
jitsi-meet@hetzner

## prerequisites

Make sure you have ansible >= 2.8 installed
```
pip3 install hcloud --user
```

## usage

```
HCLOUD_TOKEN=XXXXXXXXX  ansible-playbook -i inventory/  playbooks/setup-jitsi.yml
```
