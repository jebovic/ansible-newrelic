NewRelic
========

[![Build Status](https://travis-ci.org/jebovic/ansible-newrelic.svg?branch=master)](https://travis-ci.org/jebovic/ansible-newrelic) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.newrelic-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/newrelic)

Install and configure New Relic nrsysmond daemon

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Role Variables
--------------

```yaml
# NewRelic install configuration
newrelic_apt_key_url: https://download.newrelic.com/548C16BF.gpg
newrelic_apt_url: http://apt.newrelic.com/debian/
newrelic_config_path: /etc/newrelic
newrelic_packages:
  - newrelic-sysmond

# NewRelic basic configuration
newrelic_sysmond_key: "REPLACE_IT_WITH_YOUR_KEY"
newrelic_log_file: /var/log/newrelic/nrsysmond.log
newrelic_log_level: info
newrelic_proxy:
newrelic_ssl: off
newrelic_ssl_ca_bundle: /etc/ssl/certs/ca-certificates.crt
newrelic_ssl_ca_path: /etc/ssl/certs
newrelic_pid_file: /var/run/newrelic/nrsysmond.pid
newrelic_collector_host: collector.newrelic.com
newrelic_timeout: 30
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.newrelic }
```

Tags
----

* newrelic_config : only update config and restart service

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
