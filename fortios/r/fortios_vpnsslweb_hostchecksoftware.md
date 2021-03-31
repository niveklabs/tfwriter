# fortios_vpnsslweb_hostchecksoftware

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
module "fortios_vpnsslweb_hostchecksoftware" {
  source = "./modules/fortios/r/fortios_vpnsslweb_hostchecksoftware"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # guid - (optional) is a type of string
  guid = null
  # name - (optional) is a type of string
  name = null
  # os_type - (optional) is a type of string
  os_type = null
  # type - (optional) is a type of string
  type = null
  # version - (optional) is a type of string
  version = null

  check_item_list = [{
    action = null
    id     = null
    md5s = [{
      id = null
    }]
    target  = null
    type    = null
    version = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_item_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      id     = number
      md5s = list(object(
        {
          id = string
        }
      ))
      target  = string
      type    = string
      version = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpnsslweb_hostchecksoftware" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  guid                  = var.guid
  name                  = var.name
  os_type               = var.os_type
  type                  = var.type
  version               = var.version

  dynamic "check_item_list" {
    for_each = var.check_item_list
    content {
      action  = check_item_list.value["action"]
      id      = check_item_list.value["id"]
      target  = check_item_list.value["target"]
      type    = check_item_list.value["type"]
      version = check_item_list.value["version"]

      dynamic "md5s" {
        for_each = check_item_list.value.md5s
        content {
          id = md5s.value["id"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "guid" {
  description = "returns a string"
  value       = fortios_vpnsslweb_hostchecksoftware.this.guid
}

output "id" {
  description = "returns a string"
  value       = fortios_vpnsslweb_hostchecksoftware.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_vpnsslweb_hostchecksoftware.this.name
}

output "os_type" {
  description = "returns a string"
  value       = fortios_vpnsslweb_hostchecksoftware.this.os_type
}

output "type" {
  description = "returns a string"
  value       = fortios_vpnsslweb_hostchecksoftware.this.type
}

output "version" {
  description = "returns a string"
  value       = fortios_vpnsslweb_hostchecksoftware.this.version
}

output "this" {
  value = fortios_vpnsslweb_hostchecksoftware.this
}
```

[top](#index)