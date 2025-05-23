# Ansible OCI Modules - Training Lab

This repository provides hands-on labs for using Ansible to manage Oracle Cloud Infrastructure (OCI) resources.

## 📋 Overview

You will learn to:
- Install OCI Ansible collection
- Configure your OCI credentials
- Use Ansible to create VCNs, subnets, and compute instances in OCI etc.

## 🧰 Prerequisites

- An OCI account with proper permissions
- API Key configured in `~/.oci/config`
- Ansible 2.9+ installed
- Oracle Ansible Collection installed:


###  Oracle Linux 8
```
sudo yum-config-manager --enable ol8_developer
sudo yum-config-manager --enable ol8_developer_EPEL
sudo yum install oci-ansible-collection

#### to upgrade oci-ansible-collection
sudo yum update oci-ansible-collection
```

###  bash/Cloud-shell
```
ansible-galaxy collection install oracle.oci
```

## 🗂️ Repo Structure

```
ansible-oci-training/
├── inventory/
│   └── hosts.yml               # Localhost inventory
├── group_vars/
│   └── all.yml                 # OCI variables (update this with your tenancy-specific values)
├── labs/
│   ├── 01_auth_api.yml
│   ├── 02_auth_instance_principal.yml
│   ├── 03_auth_delegation.yml
│   ├── 04_create_vcn.yml
│   ├── 05_create_subnet.yml
│   ├── 06_launch_instance.yml
│   ├── 07_create_internet_gateway.yml
│   ├── 08_upload_object_storage.yml
│   ├── 09_create_block_volume.yml
│   └── 10_create_nsg.yml
└── README.md
```

## 🔐 OCI Configuration

### API Key
Ensure you have a valid `~/.oci/config` file:
```ini
[DEFAULT]
user=ocid1.user.oc1..xxxx
fingerprint=xx:xx:xx:xx
key_file=/home/ubuntu/.oci/oci_api_key.pem
tenancy=ocid1.tenancy.oc1..xxxx
region=us-ashburn-1
```bash
ansible-playbook labs/01_auth_api.yml
```

### Instance Principal
Ensure you have created the Dynamic Group and assigned appropriate polcies
```bash
ansible-playbook labs/02_auth_instance_principal.yml
```

### Delegation Auth
Use this option to run ansible-playbook from Cloud Shell
```bash
ansible-playbook labs/03_auth_delegation.yml
```
## 🚀 Running the Labs

Each lab file can be executed individually:

```bash
ansible-playbook -i inventory/hosts.yml labs/04_create_vcn.yml
ansible-playbook -i inventory/hosts.yml labs/05_create_subnet.yml
ansible-playbook -i inventory/hosts.yml labs/06_launch_instance.yml
ansible-playbook -i inventory/hosts.yml labs/07_create_internet_gateway.yml
ansible-playbook -i inventory/hosts.yml labs/08_upload_object_storage.yml
ansible-playbook -i inventory/hosts.yml labs/09_create_block_volume.yml
ansible-playbook -i inventory/hosts.yml labs/10_create_nsg.yml
```

## 📎 References

- [Oracle OCI Ansible Docs](https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/ansible.htm)
- [OCI Ansible GitHub](https://github.com/oracle/oci-ansible-collection)

