# checkpoint_management_data_vpn_community_star

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_data_vpn_community_star" {
  source = "./modules/checkpoint/d/checkpoint_management_data_vpn_community_star"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Object name."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_data_vpn_community_star" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "center_gateways" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_vpn_community_star.this.center_gateways
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_star.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_star.this.comments
}

output "encryption_method" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_star.this.encryption_method
}

output "encryption_suite" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_star.this.encryption_suite
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_star.this.id
}

output "ike_phase_1" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_vpn_community_star.this.ike_phase_1
}

output "ike_phase_2" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_vpn_community_star.this.ike_phase_2
}

output "mesh_center_gateways" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_vpn_community_star.this.mesh_center_gateways
}

output "override_vpn_domains" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_vpn_community_star.this.override_vpn_domains
}

output "satellite_gateways" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_vpn_community_star.this.satellite_gateways
}

output "shared_secrets" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_vpn_community_star.this.shared_secrets
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_vpn_community_star.this.tags
}

output "use_shared_secret" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_vpn_community_star.this.use_shared_secret
}

output "this" {
  value = checkpoint_management_data_vpn_community_star.this
}
```

[top](#index)