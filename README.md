Ansible Role: Solr
=========

An Ansible role that installs Apache Solr in either a standalone or replicated environment. Test with Solr version 5.3.1.

Requirements
------------

You must be running a Linux OS that has systemd enabled by default (RHEL 7, CentOS 7, Ubuntu 15.04+, Debian 8, etc). If you would like to run
a seperate Zookeeper cluster, see https://galaxy.ansible.com/detail#/role/6555

Role Variables
--------------

Version of Solr to install.

	solr_version: 5.3.1

Zookeeper Connection String. Use 127.0.0.1:2181/solr to use the Zookeeper server that comes with Solr.

	solr_zookeeper_connect_string: 127.0.0.1:2181/solr

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
	    solr_version: 5.4.0
	    solr_zookeeper_connect_string: 192.168.0.1:2181,192.168.0.2:2181,192.168.0.3:2181/solr

	  roles:
	    - solr


License
-------

BSD

Author Information
------------------

Kevin Coakley (https://github.com/kevincoakley)
