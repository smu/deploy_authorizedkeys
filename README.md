# deploy_authorizedkeys

Simple Playbook for distributing several SSH keys into a account.
Ensures that only the SSH keys specified in the variable file are distributed on the target system.

The playbook creates an `~/.ssh/authorized_keys` based on the public keys defined in `vars/HOSTNAME.yml`.
If `vars/HOSTNAME.yml` does not exists `vars/default.yml` is used. In `vars/HOSTNAME.yml` the name of the 
accound needs to be defined.

Public and privates ssh keys can be stored in `files/ssh_keys` following the pattern `username_hostname[.pub]`.
If present these files are transfered to the server and written to `~/.ssh/id_rda[.pub]`.

