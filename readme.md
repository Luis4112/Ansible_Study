# Ansible — Learning Journal

Personal notes and playbooks as I learn Ansible, coming from a 
RHCSA/Linux background. Documenting what works, what broke, and why.

## Context

I'm a Linux sysadmin in training (CCNA certified, RHCSA in progress) 
using Ansible to automate what I've been doing manually on Rocky Linux 9.

## Playbooks

### hardeningnew.yml
Automates basic SSH and firewall hardening on a fresh Rocky Linux install.
Learned: semanage needs full path in Ansible, dependencies must be 
installed before use, order of operations matters for SELinux + sshd.

### nginx.yml
Simple nginx install and enable. First playbook — mainly to understand 
idempotency in practice.

## Lessons learned the hard way (so far. WIP)

- YAML indentation will humble you
- Always install dependencies as the first task - learned this the hard way.
- ignore_errors: true is a crutch, not a solution
- Run playbooks twice — changed=0 on second run means it's clean
