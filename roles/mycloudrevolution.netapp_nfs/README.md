netapp_nfs
=========

Creates End-to-End a new NFS Export:

* Aggregate
* Broadcast Domain
* SVM
* Interface
* Export Policy 
* Volume
* Verify

Requirements
------------

Python3 netapp-lib or later. Install using ```pip install netapp-lib```

Role Variables
--------------

```yaml
create_aggr: true
create_svm: true
create_broadcast: true
create_interface: true
create_vol: true
create_nfs: true
create_export: true
verify_export: false

aggr_name: aggr_data002
broadcast_name: data_domain
broadcast_ports: ["netapp-01:e0a", "netapp-01:e0b"]
broadcast_ports_default: ["netapp-01:e0c", "netapp-01:e0d"]
if_home_port: e0b
if_home_node: netapp-01
if_address: 10.0.2.13
if_netmask: 255.255.255.0
vserver_name: data002
vol_name: vol_data002
vol_size: 1024
vol_size_unit: mb
export_policy_name: data002
export_policy_rule_client: 10.0.2.0/24
mount_directory: /mnt/verify
```

Dependencies
------------

Collections: netapp.ontap

```
ansible-galaxy collection install netapp.ontap
```

Example Playbook
----------------

```yaml
- name: NetApp NFS Setup
  hosts: localhost
  gather_facts: no
  vars:
    create_aggr: true
    create_svm: true
    create_broadcast: true
    create_interface: true
    create_vol: true
    create_nfs: true
    create_export: true
    verify_export: false
    netapp_hostname: 10.0.2.11
    netapp_username: admin
    netapp_password: Passw0rd!
  roles:
    - netapp_nfs
```

License
-------

GNU Lesser General Public License v3.0

Author Information
------------------

Markus Kraus [@vMarkus_K](https://twitter.com/vMarkus_K)

MY CLOUD-(R)EVOLUTION [mycloudrevolution.com](http://mycloudrevolution.com/)