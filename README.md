ansible-role-solr
=================

[![Build Status](https://travis-ci.org/kevincoakley/ansible-role-solr.svg?branch=master)](https://travis-ci.org/kevincoakley/ansible-role-solr)

An Ansible role that installs Apache Solr in either a standalone or replicated environment. Test with Solr version 8.2.0 on CentOS 7 and Ubuntu 18.04.

Requirements
------------

If you would like to run a separate Zookeeper cluster, see https://galaxy.ansible.com/kevincoakley/zookeeper

Role Variables
--------------

Version of Solr to install.

	solr_version: 8.2.0

Zookeeper Connection String. Use 127.0.0.1:2181 to use the Zookeeper server that comes with Solr.

	solr_zookeeper_connect_string: 127.0.0.1:2181

Solr home/data directory.

	solr_home: /mnt/solr/solr

The port that Solr should listen on.

	solr_port: 8983

The Amount of memory that should be allocated to Solr.

	solr_memory: 512m


Dependencies
------------

None

Example Playbook
----------------

Example solr_playbook.yml:

	- hosts: solr
	  sudo: yes

	  vars:
	    solr_version: 8.2.0
	    solr_zookeeper_connect_string: 192.168.0.1:2181,192.168.0.2:2181,192.168.0.3:2181/solr

	  roles:
	    - solr


License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)
