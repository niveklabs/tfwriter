# fortios_firewall_internetservicecustomgroup

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
module "fortios_firewall_internetservicecustomgroup" {
  source = "./modules/fortios/r/fortios_firewall_internetservicecustomgroup"

  # comment - (optional) is a type of string
  comment = null
  # name - (optional) is a type of string
  name = null

  member = [{
    name = null
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

variable "name" {
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
resource "fortios_firewall_internetservicecustomgroup" "this" {
  comment = var.comment
  name    = var.name

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
output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservicecustomgroup.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetservicecustomgroup.this.name
}

output "this" {
  value = fortios_firewall_internetservicecustomgroup.this
}
```

[top](#index)