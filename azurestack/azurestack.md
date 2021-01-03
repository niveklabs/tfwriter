# azurestack

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "azurestack" {
  version = "0.9.0"

  # arm_endpoint - (optional) is a type of string
  arm_endpoint = null
  # client_certificate_password - (optional) is a type of string
  client_certificate_password = null
  # client_certificate_path - (optional) is a type of string
  client_certificate_path = null
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # skip_credentials_validation - (optional) is a type of bool
  skip_credentials_validation = null
  # skip_provider_registration - (optional) is a type of bool
  skip_provider_registration = null
  # subscription_id - (optional) is a type of string
  subscription_id = null
  # tenant_id - (optional) is a type of string
  tenant_id = null
}
```

[top](#index)

### Resources


- [azurestack_availability_set](./r/azurestack_availability_set.md)

- [azurestack_dns_a_record](./r/azurestack_dns_a_record.md)

- [azurestack_dns_zone](./r/azurestack_dns_zone.md)

- [azurestack_lb](./r/azurestack_lb.md)

- [azurestack_lb_backend_address_pool](./r/azurestack_lb_backend_address_pool.md)

- [azurestack_lb_nat_pool](./r/azurestack_lb_nat_pool.md)

- [azurestack_lb_nat_rule](./r/azurestack_lb_nat_rule.md)

- [azurestack_lb_probe](./r/azurestack_lb_probe.md)

- [azurestack_lb_rule](./r/azurestack_lb_rule.md)

- [azurestack_local_network_gateway](./r/azurestack_local_network_gateway.md)

- [azurestack_managed_disk](./r/azurestack_managed_disk.md)

- [azurestack_network_interface](./r/azurestack_network_interface.md)

- [azurestack_network_security_group](./r/azurestack_network_security_group.md)

- [azurestack_network_security_rule](./r/azurestack_network_security_rule.md)

- [azurestack_public_ip](./r/azurestack_public_ip.md)

- [azurestack_resource_group](./r/azurestack_resource_group.md)

- [azurestack_route](./r/azurestack_route.md)

- [azurestack_route_table](./r/azurestack_route_table.md)

- [azurestack_storage_account](./r/azurestack_storage_account.md)

- [azurestack_storage_blob](./r/azurestack_storage_blob.md)

- [azurestack_storage_container](./r/azurestack_storage_container.md)

- [azurestack_subnet](./r/azurestack_subnet.md)

- [azurestack_template_deployment](./r/azurestack_template_deployment.md)

- [azurestack_virtual_machine](./r/azurestack_virtual_machine.md)

- [azurestack_virtual_machine_extension](./r/azurestack_virtual_machine_extension.md)

- [azurestack_virtual_machine_scale_set](./r/azurestack_virtual_machine_scale_set.md)

- [azurestack_virtual_network](./r/azurestack_virtual_network.md)

- [azurestack_virtual_network_gateway](./r/azurestack_virtual_network_gateway.md)

- [azurestack_virtual_network_gateway_connection](./r/azurestack_virtual_network_gateway_connection.md)


[top](#index)

### Datasources


- [azurestack_client_config](./d/azurestack_client_config.md)

- [azurestack_network_interface](./d/azurestack_network_interface.md)

- [azurestack_network_security_group](./d/azurestack_network_security_group.md)

- [azurestack_platform_image](./d/azurestack_platform_image.md)

- [azurestack_public_ip](./d/azurestack_public_ip.md)

- [azurestack_resource_group](./d/azurestack_resource_group.md)

- [azurestack_route_table](./d/azurestack_route_table.md)

- [azurestack_storage_account](./d/azurestack_storage_account.md)

- [azurestack_subnet](./d/azurestack_subnet.md)

- [azurestack_virtual_network](./d/azurestack_virtual_network.md)

- [azurestack_virtual_network_gateway](./d/azurestack_virtual_network_gateway.md)


[top](#index)