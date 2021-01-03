# fortios_firewall_identitybasedroute

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewall_identitybasedroute" {
  source = "./modules/fortios/r/fortios_firewall_identitybasedroute"

  # comments - (optional) is a type of string
  comments = null
  # name - (required) is a type of string
  name = null

  rule = [{
    device  = null
    gateway = null
    groups = [{
      name = null
    }]
    id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      device  = string
      gateway = string
      groups = list(object(
        {
          name = string
        }
      ))
      id = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_identitybasedroute" "this" {
  comments = var.comments
  name     = var.name

  dynamic "rule" {
    for_each = var.rule
    content {
      device  = rule.value["device"]
      gateway = rule.value["gateway"]
      id      = rule.value["id"]

      dynamic "groups" {
        for_each = rule.value.groups
        content {
          name = groups.value["name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = fortios_firewall_identitybasedroute.this.comments
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_identitybasedroute.this.id
}

output "this" {
  value = fortios_firewall_identitybasedroute.this
}
```

[top](#index)