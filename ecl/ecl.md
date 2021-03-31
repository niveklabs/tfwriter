# ecl

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "ecl" {
  version = "1.13.0"

  # auth_url - (optional) is a type of string
  auth_url = null
  # cacert_file - (optional) is a type of string
  cacert_file = null
  # cert - (optional) is a type of string
  cert = null
  # cloud - (optional) is a type of string
  cloud = null
  # default_domain - (optional) is a type of string
  default_domain = null
  # domain_id - (optional) is a type of string
  domain_id = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # endpoint_type - (optional) is a type of string
  endpoint_type = null
  # force_sss_endpoint - (optional) is a type of string
  force_sss_endpoint = null
  # insecure - (optional) is a type of bool
  insecure = null
  # key - (optional) is a type of string
  key = null
  # password - (optional) is a type of string
  password = null
  # project_domain_id - (optional) is a type of string
  project_domain_id = null
  # project_domain_name - (optional) is a type of string
  project_domain_name = null
  # region - (optional) is a type of string
  region = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
  # tenant_name - (optional) is a type of string
  tenant_name = null
  # token - (optional) is a type of string
  token = null
  # user_domain_id - (optional) is a type of string
  user_domain_id = null
  # user_domain_name - (optional) is a type of string
  user_domain_name = null
  # user_id - (optional) is a type of string
  user_id = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Resources


- [ecl_baremetal_keypair_v2](./r/ecl_baremetal_keypair_v2.md)

- [ecl_baremetal_server_v2](./r/ecl_baremetal_server_v2.md)

- [ecl_compute_instance_v2](./r/ecl_compute_instance_v2.md)

- [ecl_compute_keypair_v2](./r/ecl_compute_keypair_v2.md)

- [ecl_compute_volume_attach_v2](./r/ecl_compute_volume_attach_v2.md)

- [ecl_compute_volume_v2](./r/ecl_compute_volume_v2.md)

- [ecl_dedicated_hypervisor_license_v1](./r/ecl_dedicated_hypervisor_license_v1.md)

- [ecl_dedicated_hypervisor_server_v1](./r/ecl_dedicated_hypervisor_server_v1.md)

- [ecl_dns_recordset_v2](./r/ecl_dns_recordset_v2.md)

- [ecl_dns_zone_v2](./r/ecl_dns_zone_v2.md)

- [ecl_imagestorages_image_v2](./r/ecl_imagestorages_image_v2.md)

- [ecl_imagestorages_member_accepter_v2](./r/ecl_imagestorages_member_accepter_v2.md)

- [ecl_imagestorages_member_v2](./r/ecl_imagestorages_member_v2.md)

- [ecl_network_common_function_gateway_v2](./r/ecl_network_common_function_gateway_v2.md)

- [ecl_network_gateway_interface_v2](./r/ecl_network_gateway_interface_v2.md)

- [ecl_network_internet_gateway_v2](./r/ecl_network_internet_gateway_v2.md)

- [ecl_network_load_balancer_v2](./r/ecl_network_load_balancer_v2.md)

- [ecl_network_network_v2](./r/ecl_network_network_v2.md)

- [ecl_network_port_v2](./r/ecl_network_port_v2.md)

- [ecl_network_public_ip_v2](./r/ecl_network_public_ip_v2.md)

- [ecl_network_static_route_v2](./r/ecl_network_static_route_v2.md)

- [ecl_network_subnet_v2](./r/ecl_network_subnet_v2.md)

- [ecl_provider_connectivity_tenant_connection_request_v2](./r/ecl_provider_connectivity_tenant_connection_request_v2.md)

- [ecl_provider_connectivity_tenant_connection_v2](./r/ecl_provider_connectivity_tenant_connection_v2.md)

- [ecl_rca_user_v1](./r/ecl_rca_user_v1.md)

- [ecl_security_host_based_v1](./r/ecl_security_host_based_v1.md)

- [ecl_security_network_based_device_ha_v1](./r/ecl_security_network_based_device_ha_v1.md)

- [ecl_security_network_based_device_single_v1](./r/ecl_security_network_based_device_single_v1.md)

- [ecl_security_network_based_waf_single_v1](./r/ecl_security_network_based_waf_single_v1.md)

- [ecl_sss_approval_request_v1](./r/ecl_sss_approval_request_v1.md)

- [ecl_sss_tenant_v1](./r/ecl_sss_tenant_v1.md)

- [ecl_sss_user_v1](./r/ecl_sss_user_v1.md)

- [ecl_storage_virtualstorage_v1](./r/ecl_storage_virtualstorage_v1.md)

- [ecl_storage_volume_v1](./r/ecl_storage_volume_v1.md)

- [ecl_vna_appliance_v1](./r/ecl_vna_appliance_v1.md)


[top](#index)

### Datasources


- [ecl_baremetal_availability_zone_v2](./d/ecl_baremetal_availability_zone_v2.md)

- [ecl_baremetal_flavor_v2](./d/ecl_baremetal_flavor_v2.md)

- [ecl_baremetal_keypair_v2](./d/ecl_baremetal_keypair_v2.md)

- [ecl_compute_flavor_v2](./d/ecl_compute_flavor_v2.md)

- [ecl_compute_keypair_v2](./d/ecl_compute_keypair_v2.md)

- [ecl_dns_zone_v2](./d/ecl_dns_zone_v2.md)

- [ecl_imagestorages_image_v2](./d/ecl_imagestorages_image_v2.md)

- [ecl_network_common_function_gateway_v2](./d/ecl_network_common_function_gateway_v2.md)

- [ecl_network_common_function_pool_v2](./d/ecl_network_common_function_pool_v2.md)

- [ecl_network_fic_gateway_v2](./d/ecl_network_fic_gateway_v2.md)

- [ecl_network_gateway_interface_v2](./d/ecl_network_gateway_interface_v2.md)

- [ecl_network_internet_gateway_v2](./d/ecl_network_internet_gateway_v2.md)

- [ecl_network_internet_service_v2](./d/ecl_network_internet_service_v2.md)

- [ecl_network_load_balancer_plan_v2](./d/ecl_network_load_balancer_plan_v2.md)

- [ecl_network_network_v2](./d/ecl_network_network_v2.md)

- [ecl_network_port_v2](./d/ecl_network_port_v2.md)

- [ecl_network_public_ip_v2](./d/ecl_network_public_ip_v2.md)

- [ecl_network_qos_options_v2](./d/ecl_network_qos_options_v2.md)

- [ecl_network_static_route_v2](./d/ecl_network_static_route_v2.md)

- [ecl_network_subnet_v2](./d/ecl_network_subnet_v2.md)

- [ecl_sss_tenant_v1](./d/ecl_sss_tenant_v1.md)

- [ecl_storage_virtualstorage_v1](./d/ecl_storage_virtualstorage_v1.md)

- [ecl_storage_volume_v1](./d/ecl_storage_volume_v1.md)

- [ecl_storage_volumetype_v1](./d/ecl_storage_volumetype_v1.md)

- [ecl_vna_appliance_v1](./d/ecl_vna_appliance_v1.md)


[top](#index)