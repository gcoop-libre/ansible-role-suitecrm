Ansible Role: SuiteCRM
======================

This role installs [SuiteCRM](https://suitecrm.com). Default value for `suitecrm_repo` variable is SuiteCRM official repository [github official repo](https://github.com/salesagility/SuiteCRM).

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

* suitecrm_repo_name: SuiteCRM
* suitecrm_repo: "https://github.com/salesagility/SuiteCRM.git"
* suitecrm_repo_key_file: [sshkey path, optional - can be used to specify the ssh key to use when cloning]
* suitecrm_version: v7.8.3
* suitecrm_repo_clean: false
* suitecrm_dest: /var/www/html/suitecrm
* suitecrm_mysql_user: Database user
* suitecrm_mysql_user_password: Database user password
* suitecrm_mysql_db: Database name
* suitecrm_mysql_host: Database host
* suitecrm_admin_user_name: Admin user_name
* suitecrm_admin_password: Admin password
* suitecrm_setup_system_name: SuiteCRM deployed with Ansible
* suitecrm_setup_site_url: "http://localhost/suitecrm"
* suitecrm_log_dir: /var/log/suitecrm
* suitecrm_default_language: es_ES
* suitecrm_translations_file: URL of the translations file
* suitecrm_remote_user: debian
* suitecrm_apache_user: www-data
* suitecrm_apache_group: www-data
* suitecrm_install_from_scratch: true (set to false to clone the repo and set permissions only)
* suitecrm_install_translations: true
* suitecrm_composer_install: true
* suitecrm_composer_no_dev: true

Variable `suitecrm_version` is SuiteCRM version (git branch or tag) you want to install.
We strongly recommend [LTS versions](https://suitecrm.com/lts/).

Dependencies
------------

This role depends on `gcoop-libre.deploy-git-repos`

Example Playbook
----------------

    - hosts: servers
      become: yes
      suitecrm_remote_user: debian

      roles:
        - role: gcoop-libre.suitecrm


License
-------

GPLv2

Author Information
------------------

Created with love by [gcoop Cooperativa de Software Libre](http://gcoop.coop).
