# checkpoint_management_data_access_role

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
module "checkpoint_management_data_access_role" {
  source = "./modules/checkpoint/d/checkpoint_management_data_access_role"

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
data "checkpoint_management_data_access_role" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_role.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_role.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_role.this.id
}

output "machines" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_access_role.this.machines
}

output "networks" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_role.this.networks
}

output "remote_access_clients" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_role.this.remote_access_clients
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_role.this.tags
}

output "users" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_access_role.this.users
}

output "this" {
  value = checkpoint_management_data_access_role.this
}
```

[top](#index)