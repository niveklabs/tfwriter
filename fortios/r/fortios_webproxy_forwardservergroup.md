# fortios_webproxy_forwardservergroup

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
module "fortios_webproxy_forwardservergroup" {
  source = "./modules/fortios/r/fortios_webproxy_forwardservergroup"

  # affinity - (optional) is a type of string
  affinity = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # group_down_option - (optional) is a type of string
  group_down_option = null
  # ldb_method - (optional) is a type of string
  ldb_method = null
  # name - (optional) is a type of string
  name = null

  server_list = [{
    name   = null
    weight = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "affinity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_down_option" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldb_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      weight = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_webproxy_forwardservergroup" "this" {
  # affinity - (optional) is a type of string
  affinity = var.affinity
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # group_down_option - (optional) is a type of string
  group_down_option = var.group_down_option
  # ldb_method - (optional) is a type of string
  ldb_method = var.ldb_method
  # name - (optional) is a type of string
  name = var.name

  dynamic "server_list" {
    for_each = var.server_list
    content {
      # name - (optional) is a type of string
      name = server_list.value["name"]
      # weight - (optional) is a type of number
      weight = server_list.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "affinity" {
  description = "returns a string"
  value       = fortios_webproxy_forwardservergroup.this.affinity
}

output "group_down_option" {
  description = "returns a string"
  value       = fortios_webproxy_forwardservergroup.this.group_down_option
}

output "id" {
  description = "returns a string"
  value       = fortios_webproxy_forwardservergroup.this.id
}

output "ldb_method" {
  description = "returns a string"
  value       = fortios_webproxy_forwardservergroup.this.ldb_method
}

output "name" {
  description = "returns a string"
  value       = fortios_webproxy_forwardservergroup.this.name
}

output "this" {
  value = fortios_webproxy_forwardservergroup.this
}
```

[top](#index)