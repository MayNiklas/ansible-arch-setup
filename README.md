ansible-arch-setup
=========
[![Build Status](https://travis-ci.com/MayNiklas/ansible-arch-setup.svg?branch=main)](https://travis-ci.com/MayNiklas/ansible-arch-setup)
[![Lines Of Code](https://tokei.rs/b1/github/MayNiklas/ansible-arch-setup?category=lines)](https://github.com/XAMPPRocky/tokei)
[![Lines Of Code](https://tokei.rs/b1/github/MayNiklas/ansible-arch-setup?category=code)](https://github.com/XAMPPRocky/tokei)
[![Lines Of Code](https://tokei.rs/b1/github/MayNiklas/ansible-arch-setup?category=files)](https://github.com/XAMPPRocky/tokei)

- has to be executed while running from the Arch install media
- repartitions the drive
- creates bootloader partition
- creates /root partition
- creates filesystems
- mounts filesystems
- ranks arch mirrors
- runs pacstrap
- installs drivers
- generates fstab
- sets up local timezone
- generates locales
- sets hostname
- creates new initramfs
- sets up grub
- creates user including ssh key
- creates keyboard language files
- installs xorg
- installs kde plasma
- gives passwordless sudo access to wheel group
- reboots


Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
