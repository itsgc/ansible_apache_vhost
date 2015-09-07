## Ansible Playbook for LAMP Stack with vhosts support
This is an experimental collection of ansible playbooks to figure out a satisfactory LAMP setup that is reasonably secure for production use.

Currently uses ready-made roles. I need to find workarounds to a few issues, namely:
- I can't figure out how to create a vars file for apache that pulls documentroot and servername from the inventory rather than hardcoding them in it
- The directory structure is bare, should be improved
- All the actions involving a virtualhosts should be within a single task. One to add a vhost, one to remove it.

## Requirements
- Ansible role for MySQL - https://github.com/geerlingguy/ansible-role-mysql
- Ansible role for Apache 2.x - https://github.com/geerlingguy/ansible-role-apache

## TODO
Stuff that needs to happen:
* ~~Vhosts created on the fly from hostvars rather than hardcoded data in vars/*.yml~~ -- Done using the lookup from template functionality.
* Php and PhpMyAdmin installation, with per-vhost visibility and custom path for phpmyadmin (avoid /phpmyadmin)
* Consider adding support to pull vhost doc files from git
