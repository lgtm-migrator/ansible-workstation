## [![Nabla](https://debops.org/images/debops-small.png)](https://github.com/AlbanAndrieu) roles/alban_andrieu_workstation

This file was generated by Ansigenome. Do not edit this file directly but instead have a look at the files in the ./meta/ directory.

[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Branch](http://img.shields.io/github/tag/AlbanAndrieu/ansible-workstation.svg?style=flat-square)](https://github.com/AlbanAndrieu/ansible-workstation/tree/master)
[![Donate](https://img.shields.io/gratipay/AlbanAndrieu.svg?style=flat)](https://www.gratipay.com/~AlbanAndrieu)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-alban.andrieu.workstation-660198.svg?style=flat)](https://galaxy.ansible.com/alban.andrieu/workstation)
[![Platforms](http://img.shields.io/badge/platforms-ubuntu-lightgrey.svg?style=flat)](#)


Describe your role in a few paragraphs....


### Documentation

More information about `alban.andrieu.workstation` can be found in the
TODO [official alban.andrieu.workstation documentation](https://docs.debops.org/en/latest/ansible/roles/ansible-workstation/docs/).


### Role variables

List of default variables available in the inventory:

```YAML
workstation_enabled: yes                       # Enable module

#TODO apache_directory : "httpd" #RedHat
#TODO see apache role
apache_directory : "apache2"
apache_conf_path: "/etc/{{ apache_directory }}"
#apache_log_path: "/var/log/{{ apache_directory }}"
apache_log_path: "${APACHE_LOG_DIR}"

apache_owner: "root"
apache_group: "{{ apache_owner }}"

web_base_dir: "/var/www/sample"

#user: 'albandri' #please override me
user: "{{ lookup('env','USER') }}"
#home: '~' #please override me
home: "{{ lookup('env','HOME') }}"

redshift_owner: "{{ user }}"
redshift_group: "{{ redshift_owner }}"

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
util_pkg_state: present
# Repository states: present or absent
util_repository_state: present

apt_install_multiverse_repositories: yes  # Install some repositories (see list bellow)
apt_multiverse_repositories: ["http://us.archive.ubuntu.com/ubuntu/"]          # List of sources which be added

stats_enabled: true # Turn it to false in order to be uninstall in security role
scm_enabled: no
screensaver_enabled: yes
dash_enabled: yes
classicmenu_indicator_enabled: yes
calendar_indicator_enabled: yes
pidgin_indicator_enabled: yes
weather_indicator_enabled: yes
cpufreq_indicator_enabled: yes
tlp_enabled: yes
tweak_enabled: yes
compizconfig_enabled: yes
gstreamer_enabled: yes
skype_enabled: yes
webapps_enabled: yes
pidgin_enabled: yes
nodejs_enabled: yes
mount_enabled: no
vnc_enabled: no
synergy_enabled: yes
aws_enabled: yes
scons_enabled: yes
python_enabled: yes
ansigenome_enabled: yes
apache_create_vhosts: yes
webcam_enabled: yes
keepass2_enabled: yes
plank_enabled: yes
android_enabled: yes
docker_enabled: yes
backbox_enabled: yes
smb_enabled: yes
grub_customizer_enabled: yes
cinnamon_enabled: no
plasma_enabled: no
xfce_enabled: no
make_enabled: yes

apache_vhosts_jenkins:
  - {servername: "localhost", serveradmin: "alban.andrieu@nabla.mobi", documentroot: "/var/www/jenkins"}

apache_vhosts_nabla:
  - {servername: "www.home.nabla.mobi", serveralias: "*.home.nabla.mobi", serveradmin: "alban.andrieu@nabla.mobi", documentroot: "/var/www/nabla"}

bower_version: "1.3.12"
bower_clean_cache_enabled: no
grunt_version: "0.4.5"
grunt_cli_version: "0.1.13"

redshift_options: "-l 48.86:2.34" #For Paris
```


### Detailed usage guide

Run the following command :

```bash
ansible-playbook -i hosts -c local workstation.yml -vvvv --ask-become-pass --become | tee setup.log`
ansible-playbook -i hosts -c local -v workstation.yml -vvvv --ask-sudo-pass | tee setup.log`
```

### Testing
```shell
$ ansible-galaxy install alban.andrieu.workstation
$ vagrant up
```

### Contributing

The [issue tracker](https://github.com/AlbanAndrieu/ansible-workstation/issues) is the preferred channel for bug reports, features requests and submitting pull requests.

For pull requests, editor preferences are available in the [editor config](.editorconfig) for easy use in common text editors. Read more and download plugins at <http://editorconfig.org>.

In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

### Authors and license

`roles/alban_andrieu_workstation` role was written by:

- [Alban Andrieu](nabla.mobi) | [e-mail](mailto:alban.andrieu@free.fr) | [Twitter](https://twitter.com/AlbanAndrieu)

License
-------

- License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/AlbanAndrieu/ansible-workstation/issues)!

***

This role is part of the [Nabla](https://github.com/AlbanAndrieu) project.
README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).

***

Alban Andrieu

[linkedin](fr.linkedin.com/in/nabla/)
