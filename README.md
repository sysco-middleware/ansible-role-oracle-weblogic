oracle-weblogic
===============

Ansible role to install and configure Oracle Weblogic Server.

Requirements
------------

Download oracle weblogic installers from http://www.oracle.com/technetwork/middleware/weblogic/downloads/index.html

Role Variables
--------------

**defaults file for ansible-oracle-wls**

*required if tag 'install' will be executed*

- **oracle_weblogic_version**: 12c or 11g
- **oracle_weblogic_release**: 12.2.1 or 10.3.6
- **oracle_weblogic_quick_installation**: yes or no

- **oracle_weblogic_install_type**: Complete with Examples # WebLogic Server, Coherence, Complete with Examples

- **oracle_weblogic_jar**: JAR installer path

**vars file for ansible-oracle-wls**

*it is recommended to keep these vars by default*

- **oracle_weblogic_user**: oraclefmw
- **oracle_weblogic_group**: ofmwinstall
- **oracle_weblogic_user_home**: /opt/oraclefmw

- **oracle_weblogic_oracle_home**: /opt/oraclefmw/product/oracle_home
- **oracle_weblogic_wls_home**: "{{ oracle_weblogic_oracle_home }}/wlserver"

- **oracle_weblogic_inventory_directory**: /opt/oraclefmw/inventory
- **oracle_weblogic_inventory_file**: /opt/oraclefmw/oraInst.loc

- **oracle_weblogic_response_file**: "{{ oracle_weblogic_user_home }}/wls.rsp"

- **oracle_weblogic_already_installed**: false

Dependencies
------------

- jeqo.java

Example Playbook
----------------

Go to tests/test.yml

License
-------

MIT

Author Information
------------------

Jorge Quilcate (jorge.quilcate@sysco.no)
