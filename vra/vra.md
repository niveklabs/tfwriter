---
layout: resource
title: vra
type: provider
resource: vra
---

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "vra" {
  version = "0.3.5"

  # access_token - (optional) is a type of string
  access_token = null
  # insecure - (optional) is a type of bool
  insecure = null
  # reauthorize_timeout - (optional) is a type of string
  reauthorize_timeout = null
  # refresh_token - (optional) is a type of string
  refresh_token = null
  # url - (required) is a type of string
  url = null
}
```

[top](#index)

### Resources


- [vra_block_device](./r/vra_block_device.md)

- [vra_block_device_snapshot](./r/vra_block_device_snapshot.md)

- [vra_blueprint](./r/vra_blueprint.md)

- [vra_blueprint_version](./r/vra_blueprint_version.md)

- [vra_catalog_source_blueprint](./r/vra_catalog_source_blueprint.md)

- [vra_catalog_source_entitlement](./r/vra_catalog_source_entitlement.md)

- [vra_cloud_account_aws](./r/vra_cloud_account_aws.md)

- [vra_cloud_account_azure](./r/vra_cloud_account_azure.md)

- [vra_cloud_account_gcp](./r/vra_cloud_account_gcp.md)

- [vra_cloud_account_nsxt](./r/vra_cloud_account_nsxt.md)

- [vra_cloud_account_nsxv](./r/vra_cloud_account_nsxv.md)

- [vra_cloud_account_vmc](./r/vra_cloud_account_vmc.md)

- [vra_cloud_account_vsphere](./r/vra_cloud_account_vsphere.md)

- [vra_content_source](./r/vra_content_source.md)

- [vra_deployment](./r/vra_deployment.md)

- [vra_fabric_network_vsphere](./r/vra_fabric_network_vsphere.md)

- [vra_flavor_profile](./r/vra_flavor_profile.md)

- [vra_image_profile](./r/vra_image_profile.md)

- [vra_load_balancer](./r/vra_load_balancer.md)

- [vra_machine](./r/vra_machine.md)

- [vra_network](./r/vra_network.md)

- [vra_network_ip_range](./r/vra_network_ip_range.md)

- [vra_network_profile](./r/vra_network_profile.md)

- [vra_project](./r/vra_project.md)

- [vra_storage_profile](./r/vra_storage_profile.md)

- [vra_storage_profile_aws](./r/vra_storage_profile_aws.md)

- [vra_storage_profile_azure](./r/vra_storage_profile_azure.md)

- [vra_storage_profile_vsphere](./r/vra_storage_profile_vsphere.md)

- [vra_zone](./r/vra_zone.md)


[top](#index)

### Datasources


- [vra_block_device](./d/vra_block_device.md)

- [vra_block_device_snapshots](./d/vra_block_device_snapshots.md)

- [vra_blueprint](./d/vra_blueprint.md)

- [vra_blueprint_version](./d/vra_blueprint_version.md)

- [vra_catalog_item](./d/vra_catalog_item.md)

- [vra_catalog_source_blueprint](./d/vra_catalog_source_blueprint.md)

- [vra_catalog_source_entitlement](./d/vra_catalog_source_entitlement.md)

- [vra_cloud_account_aws](./d/vra_cloud_account_aws.md)

- [vra_cloud_account_azure](./d/vra_cloud_account_azure.md)

- [vra_cloud_account_gcp](./d/vra_cloud_account_gcp.md)

- [vra_cloud_account_nsxt](./d/vra_cloud_account_nsxt.md)

- [vra_cloud_account_nsxv](./d/vra_cloud_account_nsxv.md)

- [vra_cloud_account_vmc](./d/vra_cloud_account_vmc.md)

- [vra_cloud_account_vsphere](./d/vra_cloud_account_vsphere.md)

- [vra_data_collector](./d/vra_data_collector.md)

- [vra_deployment](./d/vra_deployment.md)

- [vra_fabric_datastore_vsphere](./d/vra_fabric_datastore_vsphere.md)

- [vra_fabric_network](./d/vra_fabric_network.md)

- [vra_fabric_storage_account_azure](./d/vra_fabric_storage_account_azure.md)

- [vra_fabric_storage_policy_vsphere](./d/vra_fabric_storage_policy_vsphere.md)

- [vra_image](./d/vra_image.md)

- [vra_image_profile](./d/vra_image_profile.md)

- [vra_machine](./d/vra_machine.md)

- [vra_network](./d/vra_network.md)

- [vra_network_domain](./d/vra_network_domain.md)

- [vra_network_profile](./d/vra_network_profile.md)

- [vra_project](./d/vra_project.md)

- [vra_region](./d/vra_region.md)

- [vra_region_enumeration](./d/vra_region_enumeration.md)

- [vra_region_enumeration_aws](./d/vra_region_enumeration_aws.md)

- [vra_region_enumeration_azure](./d/vra_region_enumeration_azure.md)

- [vra_region_enumeration_gcp](./d/vra_region_enumeration_gcp.md)

- [vra_region_enumeration_vmc](./d/vra_region_enumeration_vmc.md)

- [vra_region_enumeration_vsphere](./d/vra_region_enumeration_vsphere.md)

- [vra_security_group](./d/vra_security_group.md)

- [vra_storage_profile](./d/vra_storage_profile.md)

- [vra_storage_profile_aws](./d/vra_storage_profile_aws.md)

- [vra_storage_profile_azure](./d/vra_storage_profile_azure.md)

- [vra_storage_profile_vsphere](./d/vra_storage_profile_vsphere.md)

- [vra_zone](./d/vra_zone.md)


[top](#index)