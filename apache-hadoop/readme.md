# Provisioning Hadoop HDFS server (single node) with Ansible playbook

Configure server, install and configure, Apache Hadoop.

## Ansible dependencies

community.crypto.openssh_keypair – Generate OpenSSH private and public keys

```sh
ansible-galaxy collection install community.crypto
```

## Variables

All variables for playbook are in file: inventory/hosts.yml and inventory/group_vars/hadoop-servers.yml

```yaml
HADOOP_VERSION: "3.3.1"
HADOOP_USER: hadoop
HADOOP_DATA: /home/{{ HADOOP_USER }}/hadoop_data
disk_path: /dev/vdb
vg_name: vg_hadoop_data
pvs_name: /dev/vdb1
lv_name: lv_hadoop_data
mount_point: "{{ HADOOP_DATA }}"
file_system: ext4
```