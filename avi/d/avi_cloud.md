# avi_cloud

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_cloud" {
  source = "./modules/avi/d/avi_cloud"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_cloud" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "apic_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.apic_configuration
}

output "apic_mode" {
  description = "returns a bool"
  value       = data.avi_cloud.this.apic_mode
}

output "autoscale_polling_interval" {
  description = "returns a number"
  value       = data.avi_cloud.this.autoscale_polling_interval
}

output "aws_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.aws_configuration
}

output "azure_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.azure_configuration
}

output "cloudstack_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.cloudstack_configuration
}

output "custom_tags" {
  description = "returns a list of object"
  value       = data.avi_cloud.this.custom_tags
}

output "dhcp_enabled" {
  description = "returns a bool"
  value       = data.avi_cloud.this.dhcp_enabled
}

output "dns_provider_ref" {
  description = "returns a string"
  value       = data.avi_cloud.this.dns_provider_ref
}

output "dns_resolution_on_se" {
  description = "returns a bool"
  value       = data.avi_cloud.this.dns_resolution_on_se
}

output "docker_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.docker_configuration
}

output "east_west_dns_provider_ref" {
  description = "returns a string"
  value       = data.avi_cloud.this.east_west_dns_provider_ref
}

output "east_west_ipam_provider_ref" {
  description = "returns a string"
  value       = data.avi_cloud.this.east_west_ipam_provider_ref
}

output "enable_vip_on_all_interfaces" {
  description = "returns a bool"
  value       = data.avi_cloud.this.enable_vip_on_all_interfaces
}

output "enable_vip_static_routes" {
  description = "returns a bool"
  value       = data.avi_cloud.this.enable_vip_static_routes
}

output "gcp_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.gcp_configuration
}

output "id" {
  description = "returns a string"
  value       = data.avi_cloud.this.id
}

output "ip6_autocfg_enabled" {
  description = "returns a bool"
  value       = data.avi_cloud.this.ip6_autocfg_enabled
}

output "ipam_provider_ref" {
  description = "returns a string"
  value       = data.avi_cloud.this.ipam_provider_ref
}

output "license_tier" {
  description = "returns a string"
  value       = data.avi_cloud.this.license_tier
}

output "license_type" {
  description = "returns a string"
  value       = data.avi_cloud.this.license_type
}

output "linuxserver_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.linuxserver_configuration
}

output "mtu" {
  description = "returns a number"
  value       = data.avi_cloud.this.mtu
}

output "name" {
  description = "returns a string"
  value       = data.avi_cloud.this.name
}

output "nsx_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.nsx_configuration
}

output "obj_name_prefix" {
  description = "returns a string"
  value       = data.avi_cloud.this.obj_name_prefix
}

output "openstack_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.openstack_configuration
}

output "oshiftk8s_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.oshiftk8s_configuration
}

output "prefer_static_routes" {
  description = "returns a bool"
  value       = data.avi_cloud.this.prefer_static_routes
}

output "proxy_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.proxy_configuration
}

output "rancher_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.rancher_configuration
}

output "se_group_template_ref" {
  description = "returns a string"
  value       = data.avi_cloud.this.se_group_template_ref
}

output "state_based_dns_registration" {
  description = "returns a bool"
  value       = data.avi_cloud.this.state_based_dns_registration
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_cloud.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_cloud.this.uuid
}

output "vca_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.vca_configuration
}

output "vcenter_configuration" {
  description = "returns a set of object"
  value       = data.avi_cloud.this.vcenter_configuration
}

output "vtype" {
  description = "returns a string"
  value       = data.avi_cloud.this.vtype
}

output "this" {
  value = avi_cloud.this
}
```

[top](#index)