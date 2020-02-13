# Ansible for EduVPN

## What is this?

This is a set of ansible playbooks and roles to set up and maintain a set of
EduVPN/letsconnect hosts. This is meant to be run from a bastion-host and will
connect remotely to your VPN nodes to deploy and configure them.

## Requirements

- ansible
- python-yaml (might be included with ansible, not sure)
- Up to date target hosts (make sure to apt update/upgrade)

## How it works

See wiki. I plan to document some stuff there.

## Checklist to avoid tears:

* put your hosts in `inventory/hosts`
* make sure you can connect to them without a password through ssh (by using `ssh-keys` and an `ssh-agent`, preferably)
* make sure you can `sudo` on the host. You could do passwordless `sudo`, but you can let ansible ask for a `sudo` password (RTFM for that). The `sudo` password needs to be the same on all the hosts. If you use a dedicated user for ansible, specify it in the inventory (again, RTFM)
* make sure Python works on the target host. It can be either version 2 or 3, but you should be getting rid of Python 2 (it's EOL)
* make sure your target hosts are *up to date* when you deploy with this.