# vsphere

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vsphere" {
  version = "1.24.3"

  # allow_unverified_ssl - (optional) is a type of bool
  allow_unverified_ssl = null
  # api_timeout - (optional) is a type of number
  api_timeout = null
  # client_debug - (optional) is a type of bool
  client_debug = null
  # client_debug_path - (optional) is a type of string
  client_debug_path = null
  # client_debug_path_run - (optional) is a type of string
  client_debug_path_run = null
  # password - (required) is a type of string
  password = null
  # persist_session - (optional) is a type of bool
  persist_session = null
  # rest_session_path - (optional) is a type of string
  rest_session_path = null
  # user - (required) is a type of string
  user = null
  # vcenter_server - (optional) is a type of string
  vcenter_server = null
  # vim_keep_alive - (optional) is a type of number
  vim_keep_alive = null
  # vim_session_path - (optional) is a type of string
  vim_session_path = null
  # vsphere_server - (optional) is a type of string
  vsphere_server = null
}
```

[top](#index)

### Resources


- [vsphere_compute_cluster](./r/vsphere_compute_cluster.md)

- [vsphere_compute_cluster_host_group](./r/vsphere_compute_cluster_host_group.md)

- [vsphere_compute_cluster_vm_affinity_rule](./r/vsphere_compute_cluster_vm_affinity_rule.md)

- [vsphere_compute_cluster_vm_anti_affinity_rule](./r/vsphere_compute_cluster_vm_anti_affinity_rule.md)

- [vsphere_compute_cluster_vm_dependency_rule](./r/vsphere_compute_cluster_vm_dependency_rule.md)

- [vsphere_compute_cluster_vm_group](./r/vsphere_compute_cluster_vm_group.md)

- [vsphere_compute_cluster_vm_host_rule](./r/vsphere_compute_cluster_vm_host_rule.md)

- [vsphere_content_library](./r/vsphere_content_library.md)

- [vsphere_content_library_item](./r/vsphere_content_library_item.md)

- [vsphere_custom_attribute](./r/vsphere_custom_attribute.md)

- [vsphere_datacenter](./r/vsphere_datacenter.md)

- [vsphere_datastore_cluster](./r/vsphere_datastore_cluster.md)

- [vsphere_datastore_cluster_vm_anti_affinity_rule](./r/vsphere_datastore_cluster_vm_anti_affinity_rule.md)

- [vsphere_distributed_port_group](./r/vsphere_distributed_port_group.md)

- [vsphere_distributed_virtual_switch](./r/vsphere_distributed_virtual_switch.md)

- [vsphere_dpm_host_override](./r/vsphere_dpm_host_override.md)

- [vsphere_drs_vm_override](./r/vsphere_drs_vm_override.md)

- [vsphere_entity_permissions](./r/vsphere_entity_permissions.md)

- [vsphere_file](./r/vsphere_file.md)

- [vsphere_folder](./r/vsphere_folder.md)

- [vsphere_ha_vm_override](./r/vsphere_ha_vm_override.md)

- [vsphere_host](./r/vsphere_host.md)

- [vsphere_host_port_group](./r/vsphere_host_port_group.md)

- [vsphere_host_virtual_switch](./r/vsphere_host_virtual_switch.md)

- [vsphere_license](./r/vsphere_license.md)

- [vsphere_nas_datastore](./r/vsphere_nas_datastore.md)

- [vsphere_resource_pool](./r/vsphere_resource_pool.md)

- [vsphere_role](./r/vsphere_role.md)

- [vsphere_storage_drs_vm_override](./r/vsphere_storage_drs_vm_override.md)

- [vsphere_tag](./r/vsphere_tag.md)

- [vsphere_tag_category](./r/vsphere_tag_category.md)

- [vsphere_vapp_container](./r/vsphere_vapp_container.md)

- [vsphere_vapp_entity](./r/vsphere_vapp_entity.md)

- [vsphere_virtual_disk](./r/vsphere_virtual_disk.md)

- [vsphere_virtual_machine](./r/vsphere_virtual_machine.md)

- [vsphere_virtual_machine_snapshot](./r/vsphere_virtual_machine_snapshot.md)

- [vsphere_vm_storage_policy](./r/vsphere_vm_storage_policy.md)

- [vsphere_vmfs_datastore](./r/vsphere_vmfs_datastore.md)

- [vsphere_vnic](./r/vsphere_vnic.md)


[top](#index)

### Datasources


- [vsphere_compute_cluster](./d/vsphere_compute_cluster.md)

- [vsphere_content_library](./d/vsphere_content_library.md)

- [vsphere_content_library_item](./d/vsphere_content_library_item.md)

- [vsphere_custom_attribute](./d/vsphere_custom_attribute.md)

- [vsphere_datacenter](./d/vsphere_datacenter.md)

- [vsphere_datastore](./d/vsphere_datastore.md)

- [vsphere_datastore_cluster](./d/vsphere_datastore_cluster.md)

- [vsphere_distributed_virtual_switch](./d/vsphere_distributed_virtual_switch.md)

- [vsphere_dynamic](./d/vsphere_dynamic.md)

- [vsphere_folder](./d/vsphere_folder.md)

- [vsphere_host](./d/vsphere_host.md)

- [vsphere_host_pci_device](./d/vsphere_host_pci_device.md)

- [vsphere_host_thumbprint](./d/vsphere_host_thumbprint.md)

- [vsphere_network](./d/vsphere_network.md)

- [vsphere_resource_pool](./d/vsphere_resource_pool.md)

- [vsphere_role](./d/vsphere_role.md)

- [vsphere_storage_policy](./d/vsphere_storage_policy.md)

- [vsphere_tag](./d/vsphere_tag.md)

- [vsphere_tag_category](./d/vsphere_tag_category.md)

- [vsphere_vapp_container](./d/vsphere_vapp_container.md)

- [vsphere_virtual_machine](./d/vsphere_virtual_machine.md)

- [vsphere_vmfs_disks](./d/vsphere_vmfs_disks.md)


[top](#index)