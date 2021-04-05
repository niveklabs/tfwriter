# panos_dynamic_user_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/panos/r/panos_dynamic_user_group"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # filter - (required) is a type of string
  filter = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "(required) - The dynamic user group filter"
  type        = string
}

variable "name" {
  description = "(required) - The object name"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_dynamic_user_group" "this" {
  description  = var.description
  device_group = var.device_group
  filter       = var.filter
  name         = var.name
  tags         = var.tags
  vsys         = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_dynamic_user_group.this.id
}

output "this" {
  value = panos_dynamic_user_group.this
}
```

[top](#index)