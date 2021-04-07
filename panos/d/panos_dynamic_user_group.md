# panos_dynamic_user_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_dynamic_user_group" {
  source = "./modules/panos/d/panos_dynamic_user_group"

  # device_group - (optional) is a type of string
  device_group = null
  # name - (required) is a type of string
  name = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The object name"
  type        = string
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_dynamic_user_group" "this" {
  # device_group - (optional) is a type of string
  device_group = var.device_group
  # name - (required) is a type of string
  name = var.name
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.panos_dynamic_user_group.this.description
}

output "filter" {
  description = "returns a string"
  value       = data.panos_dynamic_user_group.this.filter
}

output "id" {
  description = "returns a string"
  value       = data.panos_dynamic_user_group.this.id
}

output "tags" {
  description = "returns a list of string"
  value       = data.panos_dynamic_user_group.this.tags
}

output "this" {
  value = panos_dynamic_user_group.this
}
```

[top](#index)