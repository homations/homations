# Homations - Home Automations

## 1. Overview

Homations consists of a set of applications, which are configured and deployed via Ansible.
All applications are running inside a Docker container. You can use this project to 
run common applications for your home server.

## 2. Available Applications

### Reverse Proxy
* [Traefik](https://doc.traefik.io/traefik/) - Traefik is an open-source Application Proxy that makes publishing your services a fun and easy experience.

### DNS
* [Bind9](https://bind9.net/) - BIND 9 has evolved to be a very flexible, full-featured DNS system.

### Identity Provider
* [Keycloak](https://www.keycloak.org/) - Open Source Identity and Access Management.

### Dashboarding
* [Grafana](https://grafana.com/docs/grafana/latest/) - Grafana allows you to query, visualize, alert on and understand your metrics no matter where they are stored.

### Observability

#### Logging
* [Loki](https://grafana.com/docs/loki/latest/) - Loki is a horizontally scalable, highly available, multi-tenant log aggregation system inspired by Prometheus.
* [Promtail](https://grafana.com/docs/loki/latest/send-data/promtail/) - Promtail is an agent which ships the contents of local logs to a private Grafana Loki instance.
* [Syslog](https://github.com/syslog-ng/syslog-ng) - syslog-ng is an enhanced log daemon, supporting a wide range of input and output methods: syslog, unstructured text, queueing, SQL & NoSQL.

#### Monitoring
* [Prometheus](https://prometheus.io/) - An open-source monitoring system with a dimensional data model, flexible query language, efficient time series database and modern alerting approach.

##### Exporter
* [Bind Exporter](https://github.com/prometheus-community/bind_exporter) - Export BIND (named/dns) v9+ service metrics to Prometheus.
* [cAdvisor](https://github.com/google/cadvisor) -cAdvisor (Container Advisor) provides container users an understanding of the resource usage and performance characteristics of their running containers.
* [Node-Exporter](https://github.com/prometheus/node_exporter) - Prometheus exporter for hardware and OS metrics exposed by *NIX kernels, written in Go with pluggable metric collectors.
* [MKTXP](https://github.com/akpw/mktxp) - Prometheus Exporter for Mikrotik RouterOS devices.

#### Alerting
* [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) - The Alertmanager handles alerts sent by client applications such as the Prometheus server.

### Storage / Databases
* [Influxdb](https://docs.influxdata.com/influxdb/v2/) - Scalable datastore for metrics, events, and real-time analytics.


### Others
* [Portainer](https://www.portainer.io/) - Portainer is your container management software to deploy, troubleshoot, and secure applications across cloud, datacenter, and Industrial IoT use cases.
* [Node-RED](https://nodered.org/) - Low-code programming for event-driven applications.

### Planned

#### Networking
* [MikroTik RouterOS](https://mikrotik.com/software) - RouterOS is the operating system of RouterBOARD of MikroTik network equipment.
* [Netbox](https://netboxlabs.com/docs/netbox/en/stable/) - NetBox is the leading solution for modeling and documenting modern networks.

#### Storage / Databases
* [Nextcloud](https://nextcloud.com/) - Nextcloud server, a safe home for all your data.

#### Messaging
* [Mosquitto](https://mosquitto.org/) - Eclipse Mosquitto is an open source (EPL/EDL licensed) message broker that implements the MQTT protocol versions 5.0, 3.1.1 and 3.1.

## 3. Requirements

- Ansible on your machine or a jump host
- Docker on your home server / target server

Note: We test our roles and playbook against an Ubuntu 24.04 LTS Server.

## 4. Installation

1. Clone this repository
2. Copy the `sample` in the inventory and create a new inventory (eg. homelab)
3. Read and configure your inventory according to the [Configuration](#51-configuration)
4. Execute this command and replace `<inventory>` with the name of your newly created inventory
    ```bash
    ansible-playbook -i inventory/<inventory>/inventory.yml site.yml
    ```
    *Note: You can use the [Ansible tags](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_tags.html) to limit the roles which are executed.
    TLDR: `ansible-playbook -i inventory/<inventory>/inventory.yml site.yml -t <tag_name>`*


## 5. Documentation

### 5.1 Configuration

You can override every variable defined in each roles default folder. For
sensitive information you can use the `ansible_vault.yml` file under
`inventory/<inventory>/group_vars/all`. This file is in the `.gitignore`,
meaning it won't be tracked by git. This file can optionally be encrypted with
[Ansible
vault](https://docs.ansible.com/ansible/latest/vault_guide/index.html). In the
sample inventory there is `ansible_vault_example.yml` which you can use as a
starting point. Just rename the file to `ansible_vault.yml` and you are good to
go.

### 5.2 Useful Dashboards to import to Grafana

- [Bind9](https://grafana.com/grafana/dashboards/12309-bind9-exporter-dns/): ID `12309`
- [cAdvisor](https://grafana.com/grafana/dashboards/14282-cadvisor-exporter/): ID `14282`
- [Logs](https://grafana.com/grafana/dashboards/13359-logs/) ID `13359`
- [MKTXP](https://grafana.com/grafana/dashboards/13679-mikrotik-mktxp-exporter/): ID `13679`
- [MikroTik Logs](https://grafana.com/grafana/dashboards/17139-mikrotik-loki-logs/) ID `17139`
- [Node-Exporter](https://grafana.com/grafana/dashboards/1860-node-exporter-full/): ID `1860`
- [Traefik](https://grafana.com/grafana/dashboards/17346-traefik-official-standalone-dashboard/) ID `17346`
