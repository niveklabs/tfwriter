# checkpoint_management_vpn_community_remote_access

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
module "checkpoint_management_vpn_community_remote_access" {
  source = "./modules/checkpoint/d/checkpoint_management_vpn_community_remote_access"

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
data "checkpoint_management_vpn_community_remote_access" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_vpn_community_remote_access.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_vpn_community_remote_access.this.comments
}

output "gateways" {
  description = "returns a set of string"
  value       = data.checkpoint_management_vpn_community_remote_access.this.gateways
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_vpn_community_remote_access.this.id
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_vpn_community_remote_access.this.tags
}

output "user_groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_vpn_community_remote_access.this.user_groups
}

output "this" {
  value = checkpoint_management_vpn_community_remote_access.this
}
```

[top](#index)