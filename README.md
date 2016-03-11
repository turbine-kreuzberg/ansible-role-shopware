votum.shopware
==============

This role installs the Shopware ecommerce system. It' s also possible to install Shopware plugins.

Requirements
------------

This role needs a working webserver with a pre-configured virtual host. And also:
* PHP >= v5.4
* composer
* Ioncube encoder
* MySQL database
* write permissions on the directory defined in `shopware_install_path`

Role Variables
--------------

The role uses variables, that you can also override:

* `shopware_repo_url` - repo for shopware sources. Default: `https://github.com/shopware/shopware.git`
* `shopware_install_demo_data` - should demo data be installed. Default: `true`
* `shopware_dev_mode` - when dev_mode is enabled all the additional dev dependencies of composer will be installed. Default: `false`
* `shopware_install_path` - the target installation path. Default: `/var/www/shopware`
* `shopware_base_uri` - the base URI which is basically the domain name. Default: `shopware.dev`
* `shopware_base_url` - the base URL of the shop - which is basically the base_uri plus a protocol. Default: `http://shopware.dev/`
* `shopware_version` - the shopware version to be installed (i.e. `5.1.3`). Default: `latest`
* `shopware_db_host` - the database host. Default: `localhost`
* `shopware_db_user` - the database user. Default: `root`
* `shopware_db_password` - the database password. Default: `root`
* `shopware_db_name` - the database name. Default: `shopware5`
* `shopware_admin_user` - the Shopware admin user name. Default: `shopware`
* `shopware_admin_password` - the Shopware admin password. Default: `shopware`
* `shopware_admin_name` - the Shopware's admin full name. Default: `shopware`
* `shopware_admin_emai` - the Shopware's admin email. Default: `admin@shopware.dev`
* `shopware_language` - the default language (can be either de_DE or en_GB). Default: `de_DE`
* `shopware_cli_repo` - git repo for the shopware cli tool. Default: `https://github.com/shopwareLabs/sw-cli-tools.git`
* `shopware_id` - if you have a Shopware ID put it here. Default: `yourid`
* `shopware_license_password` - the password for your Shopware ID. Default: `yourlicensepassword`
* `shopware_swtools_binary_path` - the path where the swtools binary will be downloaded to. Default: `~/bin/sw`
* `shopware_local_plugins` - if you have local plugins that you want to have installed, they should go into this list. empty by default
* `shopware_remote_plugins` - if you want to have plugins installed, put them in this list. empty by default
* `shopware_remote_plugins_demo_data` - the demodata plugins that you want to install via `shopware_install_demo_data`. Default: `- SwagDemoDataDE` Be aware that this also needs to be a list.
* `shopware_licenses` - a list of files containing licences that belong to the plugins configured under `shopware_remote_plugins`


Dependencies
------------


Example Playbook
----------------

A sample playbook might look like that:

```yaml
    - hosts: all
      become: yes
      vars_files:
        - vars/all.yml
    
      roles:
        - { role: apache }
        - { role: mysql }
        - { role: php }
        - { role: php-ioncube }
        - { role: composer }
        - { role: app, ansible_become: yes, ansible_become_user: www-data }
```

License
-------

BSD

Author Information
------------------

VOTUM GmbH
info@votum.de
