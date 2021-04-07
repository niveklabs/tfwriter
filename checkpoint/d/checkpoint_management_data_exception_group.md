# checkpoint_management_data_exception_group

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
module "checkpoint_management_data_exception_group" {
  source = "./modules/checkpoint/d/checkpoint_management_data_exception_group"

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
data "checkpoint_management_data_exception_group" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "applied_profile" {
  description = "returns a string"
  value       = data.checkpoint_management_data_exception_group.this.applied_profile
}

output "apply_on" {
  description = "returns a string"
  value       = data.checkpoint_management_data_exception_group.this.apply_on
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_exception_group.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_exception_group.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_exception_group.this.id
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_exception_group.this.tags
}

output "this" {
  value = checkpoint_management_data_exception_group.this
}
```

[top](#index)