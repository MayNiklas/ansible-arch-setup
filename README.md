ansible-arch-setup
=========
[![Build Status](https://travis-ci.com/MayNiklas/ansible-arch-setup.svg?branch=main)](https://travis-ci.com/MayNiklas/ansible-arch-setup)
[![Lines Of Code](https://tokei.rs/b1/github/MayNiklas/ansible-arch-setup?category=lines)](https://github.com/XAMPPRocky/tokei)
[![Lines Of Code](https://tokei.rs/b1/github/MayNiklas/ansible-arch-setup?category=code)](https://github.com/XAMPPRocky/tokei)
[![Lines Of Code](https://tokei.rs/b1/github/MayNiklas/ansible-arch-setup?category=files)](https://github.com/XAMPPRocky/tokei)

### To do

- encrypted root partition
- swap partition for hibernate
- migrate non essential parts of the install into [ansible-arch](https://github.com/MayNiklas/ansible-arch.git)
- dual boot with windows
- driver installation triggered via ansible facts (?)

### Role information

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

### Role Variables:
To be set in group_vars OR host_vars of your playbook

| Variable       | Description                                  | Default |
|----------------|----------------------------------------------|---------|
|`user_name`| name of the user being created | `nik` |
|`user_password`| hashed pw of the user being created | `<empty>` |
|`hostname`| hostname that should be set | `arch-workstation`|
|`install_drive`| path of the drive being used | `/dev/sda` |
|`bios_partition_suffix`| only relevant when changing the whole task by yourself | `1` |
|`boot_partition_suffix`| efi partion has the partion number 1 | `1` |
|`root_partition_suffix`| root partion has the partion number 2 | `2` |
|`bios`| set to true when you want a bios install -> conflicts with efi | `false` |
|`efi`| set to true when you want a efi install -> conflicts with bios | `false` |
|`intel`| set to true when you want to install intel-ucode & mesa | `false` |
|`amd`| set to true when you want to install amd-ucode | `false` |
|`nvidia: 1`| set to true when you want to install nvidia & nvidia-settings | `false` |
|`bluetooth: 1`| set to true when you want to configure bluetooth | `false` |
|`sshd: 1`| set to true when you want a running sshd server | `false` |
|`xorg`| set to true when you want to install xorg packages | `false` |
|`plasma`| set to true when you want to install plasma & boot into it | `false` |

### playbook
This role is used by my [ansible-arch-install](https://github.com/MayNiklas/ansible-arch-install.git) playbook. I would suggest, using it as a starting point!

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
