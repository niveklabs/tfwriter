# fortios_firewall_authportal

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
module "fortios_firewall_authportal" {
  source = "./modules/fortios/r/fortios_firewall_authportal"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # identity_based_route - (optional) is a type of string
  identity_based_route = null
  # portal_addr - (optional) is a type of string
  portal_addr = null
  # portal_addr6 - (optional) is a type of string
  portal_addr6 = null

  groups = [{
    name = null
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

variable "identity_based_route" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "portal_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "portal_addr6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups" {
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
resource "fortios_firewall_authportal" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  identity_based_route  = var.identity_based_route
  portal_addr           = var.portal_addr
  portal_addr6          = var.portal_addr6

  dynamic "groups" {
    for_each = var.groups
    content {
      name = groups.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_authportal.this.id
}

output "identity_based_route" {
  description = "returns a string"
  value       = fortios_firewall_authportal.this.identity_based_route
}

output "portal_addr" {
  description = "returns a string"
  value       = fortios_firewall_authportal.this.portal_addr
}

output "portal_addr6" {
  description = "returns a string"
  value       = fortios_firewall_authportal.this.portal_addr6
}

output "this" {
  value = fortios_firewall_authportal.this
}
```

[top](#index)