# ntp

Ansible role to deploy NTP (Network Time Protocol) service

## Requirements

The server where NTP will be installed should have access to remote NTP sources
to sync itself before being able to serve local requests. This role installs
the daemon with default parameters until non-default remote NTP sources are
desired. See variables below.

## Role Variables

ntp_pool: block of text containing pool lines to configure NTP with

Example :

    ntp_pool: |
      pool 0.fr.pool.ntp.org iburst
      pool 1.fr.pool.ntp.org iburst
      pool 2.fr.pool.ntp.org iburst
      pool 3.fr.pool.ntp.org iburst

## Dependencies

None.

## Install this role as submodule in a git repository

`git submodule add https://git.sekoya.org/mb/ntp.git roles/ntp`

## Example Playbook

    - hosts: ntp
      roles:
         - ntp
or

    - hosts: ntp
      roles:
         - { role: ntp, x: 42 }

## License

GPLv3

## Author Information

http://www.sekoya.org
