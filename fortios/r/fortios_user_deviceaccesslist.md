# fortios_user_deviceaccesslist

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
module "fortios_user_deviceaccesslist" {
  source = "./modules/fortios/r/fortios_user_deviceaccesslist"

  # default_action - (optional) is a type of string
  default_action = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null

  device_list = [{
    action = null
    device = null
    id     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "device_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      device = string
      id     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_deviceaccesslist" "this" {
  # default_action - (optional) is a type of string
  default_action = var.default_action
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (required) is a type of string
  name = var.name

  dynamic "device_list" {
    for_each = var.device_list
    content {
      # action - (optional) is a type of string
      action = device_list.value["action"]
      # device - (optional) is a type of string
      device = device_list.value["device"]
      # id - (optional) is a type of number
      id = device_list.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_action" {
  description = "returns a string"
  value       = fortios_user_deviceaccesslist.this.default_action
}

output "id" {
  description = "returns a string"
  value       = fortios_user_deviceaccesslist.this.id
}

output "this" {
  value = fortios_user_deviceaccesslist.this
}
```

[top](#index)