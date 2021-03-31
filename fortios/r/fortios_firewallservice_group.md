# fortios_firewallservice_group

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
module "fortios_firewallservice_group" {
  source = "./modules/fortios/r/fortios_firewallservice_group"

  # color - (optional) is a type of number
  color = null
  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # name - (required) is a type of string
  name = null
  # proxy - (optional) is a type of string
  proxy = null

  member = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "color" {
  description = "(optional)"
  type        = number
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
  description = "(required)"
  type        = string
}

variable "proxy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member" {
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
resource "fortios_firewallservice_group" "this" {
  color                 = var.color
  comment               = var.comment
  dynamic_sort_subtable = var.dynamic_sort_subtable
  name                  = var.name
  proxy                 = var.proxy

  dynamic "member" {
    for_each = var.member
    content {
      name = member.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = fortios_firewallservice_group.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallservice_group.this.id
}

output "proxy" {
  description = "returns a string"
  value       = fortios_firewallservice_group.this.proxy
}

output "this" {
  value = fortios_firewallservice_group.this
}
```

[top](#index)