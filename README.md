# Ansible Linux Setup playbook

## Description

The purpose of this playbook is to allow easy setup of Linux systems. This is an opinionated playbook, with most defaults catering to my specific use-cases.

This includes setting up:
- servers with docker, docker-swarm (coming soon) and k8s (coming soon)
- development servers with java, python and ansible (will add others as needed)
- development VMs
- personal computers, for games, work, etc.

## Usage

1. Copy the sample inventory directory: `cp -r inventories/sample inventories/<inv_name>`
2. Edit the `hosts.yml` file in the newly created inventory directory
3. Add any variables to `group_vars` or `host_vars` directories
4. Install ansible dependencies using: `ansible-galaxy install -r requirements.yml`
5. Run the playbook using ansible: `ansible-playbook playbooks/all.yml -i inventories/<inv_name>/hosts.yml -K`

## Tested Distributions

- Desktop:
    - Fedora 36 Workstation
    - Ubuntu 22.04
    - Pop OS 22.04
- Server:
    - Ubuntu Server 22.04
    - Debian 11

Notes: The desktop distributions tested all used the GNOME desktop

## Roles

- [Base](roles/base/README.md)
- [Docker](roles/docker/README.md)
- [Dev](roles/dev/README.md)
- [Virt](roles/virt/README.md)
- [Desktop](roles/desktop/README.md)
