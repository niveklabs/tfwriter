# fortios_firewallschedule_group

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
module "fortios_firewallschedule_group" {
  source = "./modules/fortios/r/fortios_firewallschedule_group"

  # color - (optional) is a type of number
  color = null
  # name - (required) is a type of string
  name = null

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

variable "name" {
  description = "(required)"
  type        = string
}

variable "member" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallschedule_group" "this" {
  color = var.color
  name  = var.name

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
  value       = fortios_firewallschedule_group.this.color
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallschedule_group.this.id
}

output "this" {
  value = fortios_firewallschedule_group.this
}
```

[top](#index)