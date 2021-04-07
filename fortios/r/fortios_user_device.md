# fortios_user_device

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
module "fortios_user_device" {
  source = "./modules/fortios/r/fortios_user_device"

  # alias - (optional) is a type of string
  alias = null
  # avatar - (optional) is a type of string
  avatar = null
  # category - (optional) is a type of string
  category = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # mac - (optional) is a type of string
  mac = null
  # master_device - (optional) is a type of string
  master_device = null
  # type - (optional) is a type of string
  type = null
  # user - (optional) is a type of string
  user = null

  tagging = [{
    category = null
    name     = null
    tags = [{
      name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "avatar" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "master_device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tagging" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      name     = string
      tags = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_device" "this" {
  # alias - (optional) is a type of string
  alias = var.alias
  # avatar - (optional) is a type of string
  avatar = var.avatar
  # category - (optional) is a type of string
  category = var.category
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # mac - (optional) is a type of string
  mac = var.mac
  # master_device - (optional) is a type of string
  master_device = var.master_device
  # type - (optional) is a type of string
  type = var.type
  # user - (optional) is a type of string
  user = var.user

  dynamic "tagging" {
    for_each = var.tagging
    content {
      # category - (optional) is a type of string
      category = tagging.value["category"]
      # name - (optional) is a type of string
      name = tagging.value["name"]

      dynamic "tags" {
        for_each = tagging.value.tags
        content {
          # name - (optional) is a type of string
          name = tags.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alias" {
  description = "returns a string"
  value       = fortios_user_device.this.alias
}

output "category" {
  description = "returns a string"
  value       = fortios_user_device.this.category
}

output "id" {
  description = "returns a string"
  value       = fortios_user_device.this.id
}

output "mac" {
  description = "returns a string"
  value       = fortios_user_device.this.mac
}

output "master_device" {
  description = "returns a string"
  value       = fortios_user_device.this.master_device
}

output "type" {
  description = "returns a string"
  value       = fortios_user_device.this.type
}

output "user" {
  description = "returns a string"
  value       = fortios_user_device.this.user
}

output "this" {
  value = fortios_user_device.this
}
```

[top](#index)