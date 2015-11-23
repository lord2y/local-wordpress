#Ansible playbook for local Wordpress Environment

The purpose of this idempotent playbook is to create a fully operational
Wordpress stack on your laptop with Vagrant.  
OS is Ubuntu 14.04.3 LTS.

###Playbook Tasks

 - Install Apache
 - Install MySQL and create needed database
 - Install PHP 5.x (fastcgi module)
 - All fix on php.ini and Apache  
 - Install Composer
 - Install Wordpress

###Requirements

 - Vagrant
 - Ansible

###Tools used

```sheel
ansible --version
ansible 1.9.4
  configured module search path = None
vagrant version
Installed Version: 1.7.4
Latest Version: 1.7.4

You're running an up-to-date version of Vagrant!
```

###To use this playbook

You can define some variables in `vars/vars.yml`

```yaml
---
  #Define your timezone
  timezone: "Europe/Rome"
  #Specify domain for your project
  domain: example.com
  #Specify Wordpress version based on github repository
  wp_version: 3.7.11
  #Specify variables for DB
  wp_db_name: wordpress-test
  wp_db_user: wordpress-test
  wp_db_passwd: password$1
  db_hostname: localhost
```

Then simple run:

```
shell
vagrant up
```
