# Homations - Home Automations

## Overview

Homations consists of a set of applications, which are configured and deployed via Ansible.
All applications are running inside a Docker container. You can use this project to 
run common applications for your home server.

## Available Applications

### Reverse Proxy
* [Traefik](https://doc.traefik.io/traefik/) - Traefik is an open-source Application Proxy that makes publishing your services a fun and easy experience. 

### Identity Provider
* [Keycloak](https://www.keycloak.org/) - Open Source Identity and Access Management.

### Dashboarding
* [Grafana](https://grafana.com/docs/grafana/latest/) - Grafana allows you to query, visualize, alert on and understand your metrics no matter where they are stored. 

### Observability
* [Loki](https://grafana.com/docs/loki/latest/) - Loki is a horizontally scalable, highly available, multi-tenant log aggregation system inspired by Prometheus. 
* [Promtail](https://grafana.com/docs/loki/latest/send-data/promtail/) - Promtail is an agent which ships the contents of local logs to a private Grafana Loki instance. 
* [Prometheus](https://prometheus.io/) - An open-source monitoring system with a dimensional data model, flexible query language, efficient time series database and modern alerting approach.
* [Node-Exporter](https://github.com/prometheus/node_exporter) - Prometheus exporter for hardware and OS metrics exposed by *NIX kernels, written in Go with pluggable metric collectors.
* [cAdvisor](https://github.com/google/cadvisor) -cAdvisor (Container Advisor) provides container users an understanding of the resource usage and performance characteristics of their running containers.
* [Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) - The Alertmanager handles alerts sent by client applications such as the Prometheus server.

### Storage / Databases
* [Influxdb](https://docs.influxdata.com/influxdb/v2/) - Scalable datastore for metrics, events, and real-time analytics.

### Messaging
* [Mosquitto](https://mosquitto.org/) - Eclipse Mosquitto is an open source (EPL/EDL licensed) message broker that implements the MQTT protocol versions 5.0, 3.1.1 and 3.1. 

### Others
* [Portainer](https://www.portainer.io/) - Portainer is your container management software to deploy, troubleshoot, and secure applications across cloud, datacenter, and Industrial IoT use cases.

### Planned
* [Bind9](https://bind9.net/) - BIND 9 has evolved to be a very flexible, full-featured DNS system.
* [MikroTik RouterOS](https://mikrotik.com/software) - RouterOS is the operating system of RouterBOARD of MikroTik network equipment.
* [Netbox](https://netboxlabs.com/docs/netbox/en/stable/) - NetBox is the leading solution for modeling and documenting modern networks. 
* [Nextcloud](https://nextcloud.com/) - Nextcloud server, a safe home for all your data.
* [Node-RED](https://nodered.org/) - Low-code programming for event-driven applications. 

## Requirements

- Ansible on your machine or a jump host 
- Docker on your home server / target server

Note: We test our roles and playbook against an Ubuntu 24.04 LTS Server.

## Installation

Tba.

## Documentation

Tba.

