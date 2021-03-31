# fortios_system_sdnconnector

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_sdnconnector" {
  source = "./modules/fortios/d/fortios_system_sdnconnector"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_sdnconnector" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "access_key" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.access_key
  sensitive   = true
}

output "api_key" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.api_key
  sensitive   = true
}

output "azure_region" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.azure_region
}

output "client_id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.client_secret
  sensitive   = true
}

output "compartment_id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.compartment_id
}

output "compute_generation" {
  description = "returns a number"
  value       = data.fortios_system_sdnconnector.this.compute_generation
}

output "domain" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.domain
}

output "external_ip" {
  description = "returns a list of object"
  value       = data.fortios_system_sdnconnector.this.external_ip
}

output "gcp_project" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.gcp_project
}

output "group_name" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.group_name
}

output "ha_status" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.ha_status
}

output "ibm_region" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.ibm_region
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.id
}

output "key_passwd" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.key_passwd
  sensitive   = true
}

output "login_endpoint" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.login_endpoint
}

output "nic" {
  description = "returns a list of object"
  value       = data.fortios_system_sdnconnector.this.nic
}

output "oci_cert" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.oci_cert
}

output "oci_fingerprint" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.oci_fingerprint
}

output "oci_region" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.oci_region
}

output "oci_region_type" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.oci_region_type
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.password
  sensitive   = true
}

output "private_key" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.private_key
  sensitive   = true
}

output "region" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.region
}

output "resource_group" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.resource_group
}

output "resource_url" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.resource_url
}

output "route" {
  description = "returns a list of object"
  value       = data.fortios_system_sdnconnector.this.route
}

output "route_table" {
  description = "returns a list of object"
  value       = data.fortios_system_sdnconnector.this.route_table
}

output "secret_key" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.secret_key
  sensitive   = true
}

output "secret_token" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.secret_token
  sensitive   = true
}

output "server" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.server
}

output "server_port" {
  description = "returns a number"
  value       = data.fortios_system_sdnconnector.this.server_port
}

output "service_account" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.service_account
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.status
}

output "subscription_id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.subscription_id
}

output "tenant_id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.tenant_id
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.type
}

output "update_interval" {
  description = "returns a number"
  value       = data.fortios_system_sdnconnector.this.update_interval
}

output "use_metadata_iam" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.use_metadata_iam
}

output "user_id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.user_id
}

output "username" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.username
}

output "vcenter_password" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.vcenter_password
  sensitive   = true
}

output "vcenter_server" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.vcenter_server
}

output "vcenter_username" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.vcenter_username
}

output "vpc_id" {
  description = "returns a string"
  value       = data.fortios_system_sdnconnector.this.vpc_id
}

output "this" {
  value = fortios_system_sdnconnector.this
}
```

[top](#index)