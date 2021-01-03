# checkpoint_management_data_host

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
module "checkpoint_management_data_host" {
  source = "./modules/checkpoint/d/checkpoint_management_data_host"

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
data "checkpoint_management_data_host" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_host.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_host.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_host.this.groups
}

output "host_servers" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_host.this.host_servers
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_host.this.id
}

output "interfaces" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_host.this.interfaces
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.checkpoint_management_data_host.this.ipv4_address
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.checkpoint_management_data_host.this.ipv6_address
}

output "nat_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_host.this.nat_settings
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_host.this.tags
}

output "this" {
  value = checkpoint_management_data_host.this
}
```

[top](#index)