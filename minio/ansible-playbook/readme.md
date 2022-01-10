# Provisioning Min.io server with Ansible playbook

Configure server, install and configure, Min.io and Nginx

## Variables

All variables for playbook are in file: inventory/hosts.yml

```yaml
ansible_user: admin
disk_path: /dev/vdb
pvs_name: /dev/vdb1
vg_name: MinioVolGroup
lv_name: MinioLogVolume
file_system: xfs
minio_workdir: /opt/minio
mount_point: "{{ minio_workdir }}/data"
app_user: minio
minio_root_user: minio_admin
minio_root_pass: minio_admin
SSL_CERT: true
minio_domain: files.example.local
minio_server_url: "http://{{ minio_domain }}"
```


## Run playbook

```sh
ansible-playbook -i inventory/hosts.yml -e "minio_root_user=minio_admin" -e "minio_root_pass=minio_admin" setup.yml
```