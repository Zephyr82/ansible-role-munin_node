# Ansible Role: Install munin-node

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-munin-node.svg)](https://travis-ci.org/tschifftner/ansible-role-munin-node)

Installs munin-node on Debian/Ubuntu linux servers.

## Requirements

None

## Dependencies

None.

### Munin settings

More settings in ```default/main.yml```

```
# Using * can lead to ipv6 listening only, therefor use 0.0.0.0
munin_node_bind_host: '0.0.0.0'
munin_node_bind_port: '4949'

munin_node_log_level: '4'
munin_node_log_file: '/var/log/munin/munin-node.log'
munin_node_pid_file: '/var/run/munin/munin-node.pid'
munin_node_background: '1'
munin_node_setsid: '1'

munin_node_user: 'root'
munin_node_group: 'root'

munin_node_timeout: '900'
munin_node_plugin_timeout: '60'

munin_node_hostname: '{{ ansible_hostname }}'

# Regexps for files to ignore
munin_node_ingore_files:
  - '[\#~]$'
  - 'DEADJOE$'
  - '\.bak$'
  - '%$'
  - '\.dpkg-(tmp|new|old|dist)$'
  - '\.rpm(save|new)$'
  - '\.pod$'

# Define munin hosts that are allowed to access this munin node
munin_node_default_hosts_allow:
  - '^127\.0\.0\.1$'
  - '^::1$'

# Used for hosts
munin_node_hosts_allow: []

# Used for groups
munin_node_hosts_allow_combined: '{{ (munin_node_default_hosts_allow + munin_node_hosts_allow) | unique }}'

munin_node_config: []
```

## Installation

```
$ ansible-galaxy install tschifftner.munin-node
```

## Example Playbook

    - hosts: server

      roles:
        - { role: tschifftner.munin-node }

## Supported OS
Ansible          | Debian Jessie    | Ubuntu 14.04    | Ubuntu 16.04    |
:--------------: | :--------------: | :-------------: | :-------------: |
2.1              | Yes              | Yes             | Yes             |              

## License

[MIT License](http://choosealicense.com/licenses/mit/)

## Author Information

 - [Tobias Schifftner](https://twitter.com/tschifftner), [ambimax® GmbH](https://www.ambimax.de)