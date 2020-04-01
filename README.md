# jitsi-meet-hetzner
jitsi-meet@hetzner

## prerequisites

* Make sure you have ansible >= 2.8 installed
* Make sure you have python3-dns installed via package manager or via pip3 `dnspython`
* Make sure you have the pyhton module hcloud installed
```
pip3 install hcloud --user
```

* Create a API Token: https://docs.hetzner.cloud/#overview-getting-started

* Make sure you have the name of your ssh-key set in:

```
inventory/group_vars/all.yml

```

* Make sure you have a registered domain name to create needed DNS records, ou will be asked to create these records when running `provision-vm.yml` as we don't know the ip address yet:
```
jitsi.example.com. 60  IN  A  111.111.111.111
*.jitsi.example.com. 60  IN  A  111.111.111.111
```

* Make sure you have variables set in inventory/group_vars/all.yml as desribed below

## Tags
----

The following tags are available

| tags              | description
| ----------        | ----------------------------- |
| common            | the role name |
| jitsi-meet        | the role name |
| always            | tasks which need to run always |
| jitsi-letsencrypt | jitsi tasks for letsencrypt install  |
| nginx             | nginx tasks | 
| firewalld         | firewalld tasks |

## Variables
---------

| variable | description | required
| --- | --- | --- |
| hostname                      | Resolvable FQDN for you jitsi vm | yes |
| ssh_user                      | ssh user to logon vm | yes |
| ssh_keys                      | ssh keys from your Hetzner cloud account | yes |
| letsencrypt_email             | email address for use with letsencrypt  | yes |
| jitsi_meet_videobridge_secret | secret please put in vault | yes |
| jitsi_meet_jicofo_secret      | secret please put in vault | yes |
| jitsi_meet_callcontrol_secret | secret please put in vault | yes |
| jitsi_meet_jicofo_password    | secret please put in vault | yes |
| hcloud_server_type            | hcloud server type | yes |
| hcloud_location               | hcloud location | yes |
| hcloud_image                  | hcloud image | yes |


## usage for provisoning vm

```
HCLOUD_TOKEN=XXXXXXXXX  ansible-playbook -i inventory/  playbooks/provision-vm.yml
```
