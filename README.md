# Ansible Role: MySQL Community Server

[![Build Status](https://travis-ci.org/rchouinard/ansible-role-mysql-community.svg?branch=master)](https://travis-ci.org/rchouinard/ansible-role-mysql-community)

Installs the MySQL Community Server for RHEL/CentOS.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    mysql_root_pass: r@nd0mP4$5WORD

## Dependencies

* [rchouinard.mysql-community-repo](https://galaxy.ansible.com/rchouinard/mysql-community-repo/)

## Example Playbook

    - hosts: database
      roles:
        - rchouinard.mysql-community

## License

MIT

## Author Information

This role was created in 2016 by [Ryan Chouinard](https://www.ryanchouinard.com/).
