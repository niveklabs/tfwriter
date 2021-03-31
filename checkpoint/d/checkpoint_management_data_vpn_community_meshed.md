# checkpoint_management_data_vpn_community_meshed

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
module "checkpoint_management_data_vpn_community_meshed" {
  source = "./modules/checkpoint/d/checkpoint_management_data_vpn_community_meshed"

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
data "checkpoint_management_data_vpn_community_meshed" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.comments
}

output "encryption_method" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.encryption_method
}

output "encryption_suite" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.encryption_suite
}

output "gateways" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.gateways
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.id
}

output "ike_phase_1" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.ike_phase_1
}

output "ike_phase_2" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.ike_phase_2
}

output "override_vpn_domains" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.override_vpn_domains
}

output "shared_secrets" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.shared_secrets
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.tags
}

output "use_shared_secret" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_vpn_community_meshed.this.use_shared_secret
}

output "this" {
  value = checkpoint_management_data_vpn_community_meshed.this
}
```

[top](#index)