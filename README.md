# ansible-role-denyhosts

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-denyhosts.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-denyhosts)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-denyhosts-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/denyhosts)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - SSH attack prevention

## Requirements

This role requires that you have the epel repository installed.

 * https://galaxy.ansible.com/linuxhq/epel/

## Role Variables

Available variables are listed below, along with default values:

    denyhosts_admin_email: root@localhost
    denyhosts_age_reset_invalid: 10d
    denyhosts_age_reset_restricted: 25d
    denyhosts_age_reset_root: 25d
    denyhosts_age_reset_valid: 5d
    denyhosts_allowed_hosts:
      - 127.0.0.1
    denyhosts_allowed_hosts_hostname_lookup: false
    denyhosts_block_service: sshd
    denyhosts_blockport: 22
    denyhosts_daemon_log: /var/log/denyhosts
    denyhosts_daemon_log_message_format: '%(asctime)s - %(name)-12s: %(levelname)-8s %(message)s'
    denyhosts_daemon_log_time_format: '%b %d %H:%M:%S'
    denyhosts_daemon_purge: 1h
    denyhosts_daemon_sleep: 30s
    denyhosts_deny_threshold_invalid: 5
    denyhosts_deny_threshold_restricted: 1
    denyhosts_deny_threshold_root: 1
    denyhosts_deny_threshold_valid: 10
    denyhosts_etc_dir: /etc
    denyhosts_hostname_lookup: false
    denyhosts_hosts_deny: /etc/hosts.deny
    denyhosts_iptables: ''
    denyhosts_lock_file: /var/lock/subsys/denyhosts
    denyhosts_pf_table: ''
    denyhosts_pfctl_path: ''
    denyhosts_plugin_deny: /usr/bin/true
    denyhosts_plugin_purge: /usr/bin/true
    denyhosts_purge_deny: 4w
    denyhosts_purge_threshold: 0
    denyhosts_reset_on_success: false
    denyhosts_secure_log: /var/log/secure
    denyhosts_smtp_date_format: '%a, %d %b %Y %H:%M:%S %z'
    denyhosts_smtp_from: 'DenyHosts <nobody@localhost>'
    denyhosts_smtp_host: localhost
    denyhosts_smtp_password: ''
    denyhosts_smtp_port: 25
    denyhosts_smtp_subject: 'DenyHosts Report from $[HOSTNAME]'
    denyhosts_smtp_username: ''
    denyhosts_suspicious_login_report_allowed_hosts: true
    denyhosts_sync_download: true
    denyhosts_sync_download_resiliency: 5h
    denyhosts_sync_download_threshold: 3
    denyhosts_sync_interval: 1h
    denyhosts_sync_server: http://xmlrpc.denyhosts.net:9911
    denyhosts_sync_upload: true
    denyhosts_syslog_report: false
    denyhosts_userdef_failed_entry_regex: ''
    denyhosts_work_dir: /var/lib/denyhosts

## Dependencies

None
 
## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.denyhosts
          denyhosts_admin_email: denyhosts@linuxhq.org

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
