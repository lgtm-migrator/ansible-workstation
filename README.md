## workstation

  [![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)

Describe your role in a few paragraphs....




### Role variables

List of default variables available in the inventory:

```yaml
    ---
    workstation_enabled: yes                       # Enable module
    
    #TODO apache_directory : "httpd" #RedHat
    #TODO see apache role
    apache_conf_path: "/etc/apache2"
    apache_directory : "apache2"
    
    #user: 'albandri' #please override me
    user: "{{ lookup('env','USER') }}"
    #home: '~' #please override me
    home: "{{ lookup('env','HOME') }}"
    
    variety_owner: "{{ user }}"
    variety_group: "{{ variety_owner }}"
    
    variety_owner_home: "{{ home }}"
    variety_directory: "{{ variety_owner_home }}/.config/variety"
    
    dropbox_owner: "{{ user }}"
    dropbox_group: "{{ dropbox_owner }}"
    
    dropbox_owner_home: "{{ home }}"
    dropbox_directory: "{{ dropbox_owner_home }}/.dropbox"
    dropbox_user_directory: "/workspace/Dropbox"
    
    # Package states: present or installed or latest
    workstation_pkg_state: present
    # Repository states: present or absent
    workstation_repository_state: present
    
    stats_enabled: true # Turn it to false in order to be uninstall in security role
    dash_enabled: yes
    pidgin_enabled: yes
    nodejs_enabled: yes
    mount_enabled: no
    vnc_enabled: no
    synergy_enabled: yes
    aws_enabled: yes
    scons_enabled: yes
    
    apache_vhosts_kibana:
      # Additional properties: 'serveradmin, extra_parameters'.
      - {servername: "localhost", documentroot: "/var/www/kibana3"}
      
    apache_vhosts_elasticsearch:
      # Additional properties: 'serveradmin, extra_parameters'.
      - {servername: "localhost", documentroot: "/var/www/kibana3"}
```


### Detailed usage guide

Describe how to use in more detail...


### Authors and license

`workstation` role was written by:
- [Alban Andrieu](nabla.mobi) | [e-mail](mailto:alban.andrieu@free.fr) | [Twitter](https://twitter.com/AlbanAndrieu)
- License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/AlbanAndrieu/ansible-workstation/issues)!

***

README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).
