# Ansible Role to Setup ETCD Cluster

## How to Use

1. **Arrange inventory**: see [example](sample-inventory.yml)
2. **Compose your playbook:** see [example](sample-playbook.yml)
3. **Redefine variables:** see [defaults](defaults/main.yml)

### ETCD Cluster Certificates

The role sets up ETCD cluster with TLS certificates. You have two options
on where to get them:

1. Generate self-signed certificates (either CA, Server or both)
2. Provide your own certificates

You also have the option to re-generate/rewrite the certificates.

This is controlled by the following variables:

```yaml
etcd_ca_cert_generate: true
etcd_ca_cert_overwrite: false
etcd_ca_cert: ""
etcd_ca_private_key: ""
etcd_ca_cn: "etcd-ca"

etcd_server_cert_generate: true
etcd_server_cert_overwrite: false
etcd_server_cert: ""
etcd_server_private_key: ""
```

## Requirements

See [requirements](meta/main.yml)

## Role Variables

See [defaults](defaults/main.yml)

## Actions Sequence

1. [Run Preparation Tasks](tasks/prepare.yml)
2. [Install ETCD and ETCDCTL](tasks/install.yml)
3. [Manage Cluster Certificates](tasks/certificates.yml)
4. [Configure Cluster Settings](tasks/configure.yml)
5. [Check Cluster Health](tasks/check.yml)

## License

MIT

## Contributors

[Shellomir](https://github.com/shellomir) (Maintainer)
