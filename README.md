# Ansible automation for NetApp CIFS provisioning
This Ansible playbook deploys a complete NetApp SVM (Storage Virtual Machine) and CIFS configuration using a modular, role‑based architecture. It leverages the `netapp.ontap` collection and various modules to manage ONTAP resources efficiently. The structure of the playbook, along with the use of roles and variable files, ensure scalability, maintainability, and consistent parameter management across clusters, network interfaces, DNS, volumes, and CIFS shares.

## Directory Structure

The playbook is organized into the following directories and files:

```
├── main.yaml
├── roles
│   ├── create_cifs
│   ├── create_dns_server
│   ├── create_interfaces
│   ├── create_svm
│   ├── create_volume
│   └── set_route
└── var_files
    ├── clusters.yaml
    └── vars.yaml
```

### Roles

- **create_cifs**: Role to create the CIFS share.
- **create_dns_server**: Role to create the DNS server.
- **create_interfaces**: Role to create the network interface.
- **create_svm**: Role to create the SVM.
- **create_volume**: Role to create the volume.
- **set_route**: Role to set the network route.

### Variable Files

- **clusters.yaml**: Contains clusters information.
- **vars.yaml**: Contains general variables.

## Modules Used

The playbook utilizes the following modules from the `netapp.ontap` collection:

- **na_ontap_cifs_server**: Manages CIFS servers.
- **na_ontap_cifs**: Manages CIFS shares.
- **na_ontap_dns**: Configures DNS servers.
- **na_ontap_interface**: Configures network interfaces.
- **na_ontap_svm**: Manages SVMs.
- **na_ontap_volume**: Manages volumes.
- **na_ontap_net_routes**: Configures network routes.

## Prerequisites

Before running the playbook, ensure you have Ansible and the NetApp ONTAP collection installed.

### Install Ansible

```bash
pip install ansible
```

### Install NetApp ONTAP Collection

```bash
ansible-galaxy collection install netapp.ontap
```

### Verify Installed Collections

```bash
ansible-galaxy collection list
```

## Running the Playbook

To execute the playbook, use the following command:

```bash
ansible-playbook main.yaml
```

## Conclusion

This playbook is designed to streamline the process of setting up an SVM with CIFS shares on NetApp ONTAP systems. The modular approach ensures that each task is handled by a dedicated role, making the playbook easy to maintain and extend. By using variable files, the playbook can be easily adapted to different environments, enhancing its scalability.
