# checkpoint_management_data_wildcard

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
module "checkpoint_management_data_wildcard" {
  source = "./modules/checkpoint/d/checkpoint_management_data_wildcard"

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
data "checkpoint_management_data_wildcard" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_wildcard.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.id
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.ipv4_address
}

output "ipv4_mask_wildcard" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.ipv4_mask_wildcard
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.ipv6_address
}

output "ipv6_mask_wildcard" {
  description = "returns a string"
  value       = data.checkpoint_management_data_wildcard.this.ipv6_mask_wildcard
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_wildcard.this.tags
}

output "this" {
  value = checkpoint_management_data_wildcard.this
}
```

[top](#index)