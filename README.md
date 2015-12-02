ansible-role-access-user - bulk addition of universal access
============================================================

Bulk addition of universal access on the servers with the disparate access. Originally designed for the initial setup of the _ansible_ access (or someone else) to an existing server infrastructure.

Features
--------

* FreeBSD, Ubuntu, RedHat OS family support
* Optional sudo
* Multiple ssh algorithms

Configuration variables
-----------------------

We believe that these variables are best used in playbook file.

* *access_user_name* - user for which the access is create, default _\_valera\__
* *need_sudo* - need or no sudo access for _\_valera\__ , true or false

Inventory example
-----------------

* host host1.example.com configured for not to use sudo or su
* host host4.example.com configured for not to add ansible user to sudoers

```
[chaotic]
host1.example.com       ansible_ssh_user="root" ansible_become="false" ansible_ssh_private_key_file="~/.ssh/id_rsa.gogi.pub"
host2.example.com       ansible_ssh_user="ashot" ansible_ssh_private_key_file="~/.ssh/id_rsa.ashot.pub"
host3.example.com       ansible_ssh_user="givi" ansible_ssh_private_key_file="~/.ssh/id_rsa.givi.pub"
host4.example.com       need_sudo="false" ansible_ssh_user="alice" ansible_ssh_private_key_file="~/.ssh/id_rsa.alice.pub"
```

--
[![LICENSE WTFPL](wtfpl-badge-1.png)](LICENSE)

