# fortios_system_automationstitch

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
module "fortios_system_automationstitch" {
  source = "./modules/fortios/r/fortios_system_automationstitch"

  # name - (optional) is a type of string
  name = null
  # status - (required) is a type of string
  status = null
  # trigger - (required) is a type of string
  trigger = null

  action = [{
    name = null
  }]

  destination = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "trigger" {
  description = "(required)"
  type        = string
}

variable "action" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "destination" {
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
resource "fortios_system_automationstitch" "this" {
  name    = var.name
  status  = var.status
  trigger = var.trigger

  dynamic "action" {
    for_each = var.action
    content {
      name = action.value["name"]
    }
  }

  dynamic "destination" {
    for_each = var.destination
    content {
      name = destination.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_automationstitch.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_automationstitch.this.name
}

output "this" {
  value = fortios_system_automationstitch.this
}
```

[top](#index)