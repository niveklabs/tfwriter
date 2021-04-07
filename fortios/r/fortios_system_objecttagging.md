# fortios_system_objecttagging

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_objecttagging" {
  source = "./modules/fortios/r/fortios_system_objecttagging"

  # address - (optional) is a type of string
  address = null
  # category - (optional) is a type of string
  category = null
  # color - (optional) is a type of number
  color = null
  # device - (optional) is a type of string
  device = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # interface - (optional) is a type of string
  interface = null
  # multiple - (optional) is a type of string
  multiple = null

  tags = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "color" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multiple" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_objecttagging" "this" {
  # address - (optional) is a type of string
  address = var.address
  # category - (optional) is a type of string
  category = var.category
  # color - (optional) is a type of number
  color = var.color
  # device - (optional) is a type of string
  device = var.device
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # interface - (optional) is a type of string
  interface = var.interface
  # multiple - (optional) is a type of string
  multiple = var.multiple

  dynamic "tags" {
    for_each = var.tags
    content {
      # name - (optional) is a type of string
      name = tags.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = fortios_system_objecttagging.this.address
}

output "category" {
  description = "returns a string"
  value       = fortios_system_objecttagging.this.category
}

output "color" {
  description = "returns a number"
  value       = fortios_system_objecttagging.this.color
}

output "device" {
  description = "returns a string"
  value       = fortios_system_objecttagging.this.device
}

output "id" {
  description = "returns a string"
  value       = fortios_system_objecttagging.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_objecttagging.this.interface
}

output "multiple" {
  description = "returns a string"
  value       = fortios_system_objecttagging.this.multiple
}

output "this" {
  value = fortios_system_objecttagging.this
}
```

[top](#index)