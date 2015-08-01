Role Name
=========

Installs GitLab-CE https://gitlab.com/gitlab-org/gitlab-ce
#####Configurable (E-Mail,LDAP Ready)

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

````
# defaults file for ansible-gitlab-ce
config_gitlab: true
gitlab_active_directory: false
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

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

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
