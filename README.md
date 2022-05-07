# Role Prometheus-Server
This role installs and configures Prometheus server components. Prometheus is a Open Source Monitoring System.

For usage information please refer to https://man.blunix.com/roles


# Incident priorities

| Priority | Description | Action |
| --- | --- | --- |
| P1 | Critical | Text-to-speech in [monitoring-alerts](https://git.blunix.com/miscellaneous/monitoring-alerts) |
| P2 | High | List in [monitoring-alerts](https://git.blunix.com/miscellaneous/monitoring-alerts) but do not text-to-speech |
| P3 | Moderate | List in [monitoring-alerts](https://git.blunix.com/miscellaneous/monitoring-alerts) `overview.py` |
| P4 | Low | Show in webui only |

The variable `prometheus_exporter_node_textfile_system_priority` from [role-prometheus-exporters](https://git.blunix.com/ansible-roles/role-prometheus-exporters) overrides that value downwards. Example:  
Check priority: 1
System priority: 2
Actual priority in [monitoring-alerts](https://git.blunix.com/miscellaneous/monitoring-alerts): 2


# How to implement new collector with alerts
- write a collector
- add it to the role-prometheus-exporters
- add it to the prometheus-exporters play
- apply the role
- add the exporter to exporters loop in templates/etc/prometheus-server/prometheus.yml.j2 in this role
- check that the metrics come in in the prometheus webui
- create rules for the metrics


# Author Information
This role is part of *Blunix* - a full stack hosting system automated with Ansible.
Blunix GmbH provides services and support for fully fully automated hosting environments,
continuous integration/deployment/delivery and various Linux and open-source technology stacks.

```
Blunix GmbH - Consulting for Linux Hosting 24/7
Glogauer Straße 21
10999 Berlin
Germany

Website: https://www.blunix.com
E-Mail:  contact@blunix.com
gpg key: https://www.blunix.com/contact-blunix-com-gpg-key
```


# License
Apache-2.0
