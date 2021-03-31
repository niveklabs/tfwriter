# checkpoint_management_data_address_range

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
module "checkpoint_management_data_address_range" {
  source = "./modules/checkpoint/d/checkpoint_management_data_address_range"

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
  description = "(optional) - Object name. Should be unique in the domain."
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
data "checkpoint_management_data_address_range" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_address_range.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.id
}

output "ipv4_address_first" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.ipv4_address_first
}

output "ipv4_address_last" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.ipv4_address_last
}

output "ipv6_address_first" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.ipv6_address_first
}

output "ipv6_address_last" {
  description = "returns a string"
  value       = data.checkpoint_management_data_address_range.this.ipv6_address_last
}

output "nat_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_address_range.this.nat_settings
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_address_range.this.tags
}

output "this" {
  value = checkpoint_management_data_address_range.this
}
```

[top](#index)