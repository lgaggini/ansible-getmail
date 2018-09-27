# ansible-getmail

ansible-getmail is an Ansible role to install and configure getmail on a debian based OS.

It performs: 

* installation of getmail package
* creation of dedicated user and group for getmail runs
* creation of dedicated folder for getmail configurations and logs
* configuration of accounts to be retrieved by getmail (pop3 ssl, you can customize the getmairc template for other retrievers type)
* installation, start and enable of a dedicated systemd unit

## Install
### Clone
```bash
git clone https://github.com/lgaggini/ansible-getmail.git
```
## Configuration

The configuration is done by vars listed and explained in [defaults/main.yml](https://github.com/lgaggini/ansible-getmail/blob/master/defaults/main.yml) file.

## Usage

```
- name: bootstrap an ubuntu cloud image for getmail
  hosts: getmailserver
  vars_files:
    - group_vars/getmail.yml

  roles:
    - { role: getmail, tags: ['getmail'] }
```
