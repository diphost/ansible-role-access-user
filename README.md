ansible-role-access-user - bulk addition of universal access
============================================================

Bulk addition of universal access on the servers with the disparate access. Originally designed for the initial setup of the _ansible_ access (or someone else) to an existing server infrastructure.

Features
--------

* FreeBSD, Ubuntu, RedHat OS famaly support
* Optional sudo
* Multiple ssh algorithms

Configuration variables
-----------------------

We believe that these variables are best used in playbook file.

* access_user_name - user for which the access is create, default _\_valera\__
* need_sudo - need or no sudo access for __valera__

Inventory example
-----------------

* host host1.example.com configured for not to use sudo or su
* host host4.example.com configured for not to add ansible user to sudoers

```
[chaotic]
host1.example.com       ansible_ssh_user="root" become="no" ansible_ssh_private_key_file="~/.ssh/id_rsa.gogi"
host2.example.com       ansible_ssh_user="ashot" ansible_ssh_private_key_file="~/.ssh/id_rsa.ashot"
host3.example.com       ansible_ssh_user="givi" ansible_ssh_private_key_file="~/.ssh/id_rsa.givi"
host4.example.com       need_sudo="no" ansible_ssh_user="alice" ansible_ssh_private_key_file="~/.ssh/id_rsa.alice"
```

--
[![LICENSE WTFPL](wtfpl-badge-1.png)](LICENSE)

