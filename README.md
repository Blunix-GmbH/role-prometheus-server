# Role Prometheus
This role installs and configures Prometheus, a Open Source Monitoring System.

For usage information please refer to https://man.blunix.com/roles


# Incident priorities

P5 Informational
  - No notification needed
  - Show only on dashboards
  - Examples: Actions which are regular during self healing such as failover actions

P4 Low
  - Notifications during office hours / loud hours
  - Incidents that require manual intervention, but may wait up to one week
  - Priority may be increased after 1 week
  - Examples: Missed cronjobs, expiring ssl certificates, nonworking backups etc

P3 Moderate
  - Notifications during office hours immediately
  - Notifications delayed by 3 hours between 10pm and 7am
  - Incidents that may reduce functionality if unhandled, but should recover by self healing mechanism
  - Example: High cpu, high load, disk space predictions, high exception count

P2 High
  - Immediate notifications 24/7
  - Escalates to CTO after 1 hour
  - Incidents that may have major impact to infrastructure or product
  - Examples: TargetDown, NoTargetFound, high error count, high response times

P1 Critical
  - Immediate notifications 24/7
  - Notifies CTO / CEO immediately
  - Confirmed outages of product related services
  - Examples: BlackboxProbeFailed, High amount of customer facing errors


Interesting document on designing paging rules: https://docs.google.com/document/d/199PqyG3UsyXlwieHaqbGiWVa8eMWi8zzAn0YfcApr8Q/edit


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
