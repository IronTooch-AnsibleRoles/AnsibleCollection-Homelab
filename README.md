# Ansible Collection - irontooch.homelab

Establishing a HomeLab environment with some basic infrastructure items. The general idea is to deploy all the things needed to self host, and just have the ability to select what you'd like from a "shopping list".

![GitHub all releases](https://img.shields.io/github/downloads-pre/irontooch/AnsibleCollection-Homelab/total)
![GitHub repo size](https://img.shields.io/github/repo-size/IronTooch/AnsibleCollection-Homelab)
![GitHub issues](https://img.shields.io/github/issues-raw/Irontooch/AnsibleCollection-Homelab)
![GitHub Open PRs](https://badgen.net/github/open-prs/Irontooch/AnsibleCollection-Homelab)
![GitHub commits since tagged version](https://img.shields.io/github/commits-since/IronTooch/AnsibleCollection-Homelab/v0.1.0?label=commits)
![GitHub last commit](https://img.shields.io/github/last-commit/IronTooch/AnsibleCollection-Homelab)
![GitHub Release Date](https://img.shields.io/github/release-date-pre/Irontooch/AnsibleCollection-Homelab)
![GitHub Maintained](https://img.shields.io/maintenance/yes/2022)
![GitHub](https://img.shields.io/github/license/IronTooch/AnsibleCollection-Homelab)
![Forks](https://img.shields.io/github/forks/Irontooch/AnsibleCollection-Homelab.svg)
![Stars](https://img.shields.io/github/stars/Irontooch/AnsibleCollection-Homelab.svg)
![Watchers](https://img.shields.io/github/watchers/Irontooch/AnsibleCollection-Homelab.svg)
![Follow](https://img.shields.io/github/followers/IronTooch.svg?style=social&label=Follow&maxAge=2592000)

Installing from Github is accomplished via: `ansible-galaxy collection install git+https://github.com/IronTooch/AnsibleCollection-Homelab.git,master`

## Roles included

### Credentials

- cd_bitwarden

### Database

- db_missionkontrol  *(Cleanup needed)*
- db_postgres


### File Management

- fi_jirafeau *(In Progress)*

### Networking

- ne_coredns *(In Progress)*
- ne_ddclient *(In Progress)*
- ne_maas *(In Progress)*
- ne_nginx *(In Progress)*
- ne_nginxproxymanager *(In Progress)*

### PKI

- pk_stepca *(Cleanup needed)*
- pk_stepcli *(Cleanup needed)*
- pk_ejbca  *(Cleanup needed)*

### Support (Used for dependency mapping)

- su_docker *(Cleanup needed)*

### System Roles

- sy_ajenti *(In Progress)*
- sy_proxmox *(In Progress)*
- sy_vmsetup *(Cleanup needed)*
- sy_olivetin *(In Progress)*
