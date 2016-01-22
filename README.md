oracle-weblogic
===============

ansible role to install and configure oracle weblogic server, and create domains.

Requirements
------------

download oracle weblogic installers from http://www.oracle.com/technetwork/middleware/weblogic/downloads/index.html

Role Variables
--------------

**defaults file for ansible-oracle-wls**

*required if tag 'install' will be executed*

- oracle_weblogic_version: 12c
- oracle_weblogic_release: 12.2.1
- oracle_weblogic_quick_installation_type: yes # or no

- oracle_weblogic_installation_option: Complete with Examples # WebLogic Server, Coherence, Complete with Examples (only required if oracle_weblogic_quick_installation_type is no)

- oracle_wls_installers_12_2_1_1of1: roles/oracle-weblogic/files/fmw_12.2.1.0.0_wls_Disk1_1of1.zip # only required if oracle_weblogic_quick_installation_type is no
- oracle_wlsqs_installers_12_2_1_1of1: roles/oracle-weblogic/files/fmw_12.2.1.0.0_wls_quick_Disk1_1of1.zip # only required if oracle_weblogic_quick_installation_type is yes

**vars file for ansible-oracle-wls**

*it is recommended to keep these vars by default*

- oracle_weblogic_os_user: oraclefmw
- oracle_weblogic_os_group: ofmwinstall
- oracle_weblogic_oracle_home: /home/{{ oracle_weblogic_os_user }}/product/oracle_home
- oracle_weblogic_inventory_file: /home/{{ oracle_weblogic_os_user }}/oraInst.loc
- oracle_weblogic_inventory_directory: /home/{{ oracle_weblogic_os_user }}/ora_inventory

- oracle_weblogic_domains_home: /home/{{ oracle_weblogic_os_user }}/config/domains
- oracle_weblogic_apps_home: /home/{{ oracle_weblogic_os_user }}/config/apps

- oracle_wls_installers_12_2_1_1of1_checksum: 58aa613f95a2614f93e2789d15d3b4bbaa357575
- oracle_wlsqs_installers_12_2_1_1of1_checksum: dcd79a4c911e2b18a247a2dddc5691c61dc41e88

Dependencies
------------

- jeqo.java

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: oracle-weblogic
           oracle_weblogic_version: 12c
           oracle_weblogic_release: 12.2.1
           oracle_weblogic_quick_installation_type: no
           oracle_wls_installers_12_2_1_1of1: /srv/files/fmw_12.2.1.0.0_wls_Disk1_1of1.zip

License
-------

MIT

Author Information
------------------

jeqo (quilcate.jorge@gmail.com)
