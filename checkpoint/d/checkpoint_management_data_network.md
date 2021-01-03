# checkpoint_management_data_network

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_data_network" {
  source = "./modules/checkpoint/d/checkpoint_management_data_network"

  # groups - (optional) is a type of set of string
  groups = []
  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "groups" {
  description = "(optional) - Collection of group identifiers."
  type        = set(string)
  default     = null
}

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
data "checkpoint_management_data_network" "this" {
  groups = var.groups
  name   = var.name
  uid    = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "broadcast" {
  description = "returns a string"
  value       = data.checkpoint_management_data_network.this.broadcast
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_network.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_network.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_network.this.id
}

output "mask_length4" {
  description = "returns a number"
  value       = data.checkpoint_management_data_network.this.mask_length4
}

output "mask_length6" {
  description = "returns a number"
  value       = data.checkpoint_management_data_network.this.mask_length6
}

output "nat_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_network.this.nat_settings
}

output "subnet4" {
  description = "returns a string"
  value       = data.checkpoint_management_data_network.this.subnet4
}

output "subnet6" {
  description = "returns a string"
  value       = data.checkpoint_management_data_network.this.subnet6
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_network.this.tags
}

output "this" {
  value = checkpoint_management_data_network.this
}
```

[top](#index)