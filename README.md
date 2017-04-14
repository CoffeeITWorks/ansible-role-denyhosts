# ansible-role-denyhosts

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-denyhosts.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-denyhosts)

RHEL/CentOS - SSH attack prevention

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    denyhosts_admin_email: 'root@localhost'
    denyhosts_age_reset_invalid: 10d
    denyhosts_age_reset_restricted: 25d
    denyhosts_age_reset_root: 25d
    denyhosts_age_reset_valid: 5d
    denyhosts_allowed_hosts_hostname_lookup: 'no'
    denyhosts_block_service: sshd
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
    denyhosts_hostname_lookup: 'no'
    denyhosts_hosts_deny: /etc/hosts.deny
    denyhosts_lock_file: /var/lock/subsys/denyhosts
    denyhosts_purge_deny: 4w 
    denyhosts_reset_on_success: 'no'
    denyhosts_secure_log: /var/log/secure
    denyhosts_smtp_from: 'DenyHosts <nobody@localhost>'
    denyhosts_smtp_host: localhost
    denyhosts_smtp_port: 25
    denyhosts_smtp_subject: 'DenyHosts Report from $[HOSTNAME]'
    denyhosts_suspicious_login_report_allowed_hosts: 'yes'
    denyhosts_sync_download: 'no'
    denyhosts_sync_upload: 'no'
    denyhosts_syslog_report: 'no'
    denyhosts_work_dir: /var/lib/denyhosts

Additional variables not defined by default

    denyhosts_blockport: 22
    denyhosts_iptables: /usr/sbin/iptables
    denyhosts_pf_table: blacklist
    denyhosts_pfctl_path: /sbin/pfctl
    denyhosts_plugin_deny: /usr/bin/true
    denyhosts_plugin_purge: /usr/bin/true
    denyhosts_smtp_date_format: '%a, %d %b %Y %H:%M:%S %z'
    denyhosts_smtp_password: bar
    denyhosts_smtp_username: foo
    denyhosts_sync_download_resiliency: 5h
    denyhosts_sync_download_threshold: 3
    denyhosts_sync_interval: 1h
    denyhosts_sync_server: 'http://xmlrpc.denyhosts.net:9911'
    denyhosts_userdef_failed_entry_regex: '^.*$'

## Dependencies

 * https://galaxy.ansible.com/linuxhq/epel/
 
## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.denyhosts
          denyhosts_admin_email: denyhosts@linuxhq.org

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
