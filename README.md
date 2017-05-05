Ansible Role: SuiteCRM
======================

This role install [SuiteCRM](https://suitecrm.com) from [github official repo](https://github.com/salesagility/SuiteCRM).

Requirements
------------

You need a server running GNU+Linux (with rsync and unzip), Apache, PHP and MySQL. You can use the following roles:

* `gcoop-libre.apache`
* `gcoop-libre.percona-repo`
* `geerlingguy.mysql`
* `geerlingguy.php`

In the local machine `git` is required.


Role Variables
--------------

* suitecrm_version: v7.8.3
* suitecrm_dest: /var/www/html/suitecrm
* suitecrm_mysql_user: Database user
* suitecrm_mysql_user_password: Database user password
* suitecrm_mysql_db: Database name
* suitecrm_mysql_host: Database host
* suitecrm_admin_user_name: Admin user_name
* suitecrm_admin_password: Admin password
* suitecrm_setup_system_name: SuiteCRM deployed with Ansible
* suitecrm_setup_site_url: "http://localhost/suitecrm"
* suitecrm_default_language: es_ES
* suitecrm_translations_file: URL of the translations file


Variable `suitecrm_version` is SuiteCRM version you want to install, as tagged [here](https://github.com/salesagility/SuiteCRM/tags). We strongly recommend [LTS versions](https://suitecrm.com/lts/).

Dependencies
------------

This role depends on `gcoop-libre.deploy-git-repos`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      remote_user: debian

      roles:
        - role: gcoop-libre.suitecrm



License
-------

GPLv2

Author Information
------------------

This role was created in 2017 with love by [gcoop Cooperativa de Software Libre](http://gcoop.coop).
