# Ansible Role: MySQL Community Server

Installs the MySQL Community Server for RHEL/CentOS, Fedora, Debian, and Ubuntu.

## Requirements

On systems with SELinux enabled, the `libselinux-python` package may be required. This is required by the Ansible
`template` module used to build the default MySQL configuration file.

On Fedora systems using the DNF package manager, the `python2-dnf` package is required.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    mysql_root_pass:                          r@nd0mP4$5WORD
    mysql_cfg_socket:                         (distro dependent)
    mysql_cfg_pid_file:                       /var/run/mysqld/mysqld.pid
    mysql_cfg_datadir:                        /var/lib/mysql
    mysql_cfg_log_bin:                        /var/lib/mysql/mysql-bin
    mysql_cfg_log_error:                      (distro dependent)
    mysql_cfg_slow_query_log_file:            (distro dependent)
    mysql_cfg_cnffile:                        (distro dependent)
    mysql_cfg_cnfdir:                         (distro dependent)
    mysql_cfg_user:                           mysql
    mysql_cfg_default_storage_engine:         InnoDB
    mysql_cfg_port:                           3306
    mysql_cfg_key_buffer_size:                32M
    mysql_cfg_myisam_recover_options:         FORCE,BACKUP
    mysql_cfg_max_allowed_packet:             16M
    mysql_cfg_max_connect_errors:             1000000
    mysql_cfg_server_id:                      999999
    mysql_cfg_expire_logs_days:               14
    mysql_cfg_sync_binlog:                    1
    mysql_cfg_tmp_table_size:                 32M
    mysql_cfg_max_heap_table_size:            32M
    mysql_cfg_query_cache_type:               0
    mysql_cfg_query_cache_size:               0
    mysql_cfg_max_connections:                500
    mysql_cfg_thread_cache_size:              50
    mysql_cfg_open_files_limit:               65535
    mysql_cfg_table_definition_cache:         4096
    mysql_cfg_table_open_cache:               4096
    mysql_cfg_innodb_flush_method:            O_DIRECT
    mysql_cfg_innodb_log_files_in_group:      2
    mysql_cfg_innodb_log_file_size:           200M
    mysql_cfg_innodb_flush_log_at_trx_commit: 1
    mysql_cfg_innodb_file_per_table:          1
    mysql_cfg_innodb_buffer_pool_size:        1600M
    mysql_cfg_log_queries_not_using_indexes:  1
    mysql_cfg_slow_query_log:                 1

## Dependencies

* [rchouinard.mysql-community-repo](https://galaxy.ansible.com/rchouinard/mysql-community-repo/)

## Example Playbook

    - hosts: database
      roles:
        - rchouinard.mysql-community
      vars:
        mysql_root_pass: "{{ lookup('password', 'credentials/mysqlpassword length=22') }}"

## License

MIT

## Author Information

This role was created in 2016 by [Ryan Chouinard](https://www.ryanchouinard.com/).
