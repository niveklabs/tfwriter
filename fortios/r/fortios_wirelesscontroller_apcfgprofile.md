# fortios_wirelesscontroller_apcfgprofile

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
module "fortios_wirelesscontroller_apcfgprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_apcfgprofile"

  # ac_ip - (optional) is a type of string
  ac_ip = null
  # ac_port - (optional) is a type of number
  ac_port = null
  # ac_timer - (optional) is a type of number
  ac_timer = null
  # ac_type - (optional) is a type of string
  ac_type = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (optional) is a type of string
  name = null

  command_list = [{
    id           = null
    name         = null
    passwd_value = null
    type         = null
    value        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ac_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ac_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ac_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ac_type" {
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "command_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id           = number
      name         = string
      passwd_value = string
      type         = string
      value        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_apcfgprofile" "this" {
  # ac_ip - (optional) is a type of string
  ac_ip = var.ac_ip
  # ac_port - (optional) is a type of number
  ac_port = var.ac_port
  # ac_timer - (optional) is a type of number
  ac_timer = var.ac_timer
  # ac_type - (optional) is a type of string
  ac_type = var.ac_type
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # name - (optional) is a type of string
  name = var.name

  dynamic "command_list" {
    for_each = var.command_list
    content {
      # id - (optional) is a type of number
      id = command_list.value["id"]
      # name - (optional) is a type of string
      name = command_list.value["name"]
      # passwd_value - (optional) is a type of string
      passwd_value = command_list.value["passwd_value"]
      # type - (optional) is a type of string
      type = command_list.value["type"]
      # value - (optional) is a type of string
      value = command_list.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ac_ip" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apcfgprofile.this.ac_ip
}

output "ac_port" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_apcfgprofile.this.ac_port
}

output "ac_timer" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_apcfgprofile.this.ac_timer
}

output "ac_type" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apcfgprofile.this.ac_type
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apcfgprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_apcfgprofile.this.name
}

output "this" {
  value = fortios_wirelesscontroller_apcfgprofile.this
}
```

[top](#index)