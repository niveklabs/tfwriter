# fortios_firewall_internetservicegroup

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
module "fortios_firewall_internetservicegroup" {
  source = "./modules/fortios/r/fortios_firewall_internetservicegroup"

  # comment - (optional) is a type of string
  comment = null
  # direction - (optional) is a type of string
  direction = null
  # name - (optional) is a type of string
  name = null

  member = [{
    id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "direction" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetservicegroup" "this" {
  comment   = var.comment
  direction = var.direction
  name      = var.name

  dynamic "member" {
    for_each = var.member
    content {
      id = member.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "direction" {
  description = "returns a string"
  value       = fortios_firewall_internetservicegroup.this.direction
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservicegroup.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetservicegroup.this.name
}

output "this" {
  value = fortios_firewall_internetservicegroup.this
}
```

[top](#index)