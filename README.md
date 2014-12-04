Stouts.mongo
============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.mongodb.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.mongodb)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.mongodb-blue.svg?style=flat-square)](https://galaxy.ansible.com/list#/roles/982)

Ansible role which manage [MongoDB](http://www.mongodb.org/)

* Install and configure;
* Provide hanlers for restart and reload;

#### Variables

```yaml
mongodb_enabled: yes
mongodb_packages:
  - python-selinux
  - python-pymongo
  - mongodb-org

# MongoDB configuration

mongodb_conf_auth: "false"
mongodb_conf_bind_ip: 127.0.0.1
mongodb_conf_cpu: "true"
mongodb_conf_dbpath: /var/lib/mongodb/
mongodb_conf_logappend: "true"
mongodb_conf_logpath: /var/log/mongodb/mongod.log
mongodb_conf_noauth: "true"
mongodb_conf_nohints: "false"
mongodb_conf_nohttpinterface: "false"
mongodb_conf_nojournal: "true"
mongodb_conf_noprealloc: "false"
mongodb_conf_noscripting: "false"
mongodb_conf_notablescan: "false"
mongodb_conf_objcheck: "false"
mongodb_conf_port: 27017
mongodb_conf_quota: "false"
mongodb_conf_verbose: "true"
mongodb_conf_vvvv: "true"

# Log rotation

mongodb_logrotate: yes
mongodb_logrotate_options:
  - compress
  - copytruncate
  - daily
  - dateext
  - rotate 7
  - size 10M
```

#### Usage

Add `Stouts.mongodb` to your roles and set vars in your playbook file.

Example:

```yaml
- hosts: all
  roles:
    - Stouts.mongodb
  vars:
    mongodb_conf_port: 27400
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.mongodb/issues)!
