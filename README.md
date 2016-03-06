Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

The role uses variables, that you can also override:

* `shopware_repo_url` - repo to checkout. Default: `https://github.com/ShopwareAG/shopware-4.git`.
* `shopware_demo_data_url` - demo data:. Default: `http://releases.s3.shopware.com/demo_4.2.0.zip`
* `shopware_install_path` - `/var/www/shopware` by default.
* `shopware_db_host` - `localhost` by default.
* `shopware_db_name` - `shopware` by default.
* `shopware_db_password` - `shopware` by default.
* `shopware_db_user` - `shopware` by default.
* `shopware_app_path` - `/shopware` by default.
* `shopware_app_host` - `33.33.33.20` by default.


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
