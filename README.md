Role Name
=========

Installs GitLab-CE https://gitlab.com/gitlab-org/gitlab-ce
#####Configurable (E-Mail,LDAP Ready)

Default login is root/5iveL!fe

Requirements
------------

None

Role Variables
--------------

````
---
# defaults file for ansible-gitlab-ce
config_gitlab: false
gitlab_active_directory: false
gitlab_apt_key: https://packages.gitlab.com/gpg.key
gitlab_apt_repos:
  - deb https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu/ trusty main
  - deb-src https://packages.gitlab.com/gitlab/gitlab-ce/ubuntu/ trusty main
gitlab_ce_dl_package: gitlab-ce_8.0.5-ce.0_amd64.deb
gitlab_ce_dl_url: https://packages.gitlab.com/gitlab/gitlab-ce/packages/ubuntu/trusty
gitlab_email_display_name: '{{ ansible_hostname }}'
gitlab_email_enabled: false  #define here or in group_vars/group
gitlab_email_from: '{{ ansible_hostname }}@{{ smtp_domain_name }}'
gitlab_email_reply_to: '{{ gitlab_email_from }}'
gitlab_ldap_base_dn: []  #define here or in group_vars/group
gitlab_ldap_bind_dn: []  #define here or in group_vars/group
gitlab_ldap_bind_pass: []  #define here or in group_vars/group
gitlab_ldap_enabled: false  #define here or in group_vars/group
gitlab_ldap_servers: [] #define here or in group_vars/group
#  - host: 'dc01.{{ pri_domain_name }}'
#    role: main
#  - host: 'dc02.{{ pri_domain_name }}'
#    role: secondary
pri_domain_name: example.org  #defines primary domain name...define here or globally in group_vars/all
````

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: mrlesmithjr.gitlab-ce }

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com
