# fortios_switchcontroller_quarantine

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
module "fortios_switchcontroller_quarantine" {
  source = "./modules/fortios/r/fortios_switchcontroller_quarantine"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # quarantine - (optional) is a type of string
  quarantine = null

  targets = [{
    description = null
    entry_id    = null
    mac         = null
    tag = [{
      tags = null
    }]
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

variable "quarantine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "targets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      entry_id    = number
      mac         = string
      tag = list(object(
        {
          tags = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_quarantine" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  quarantine            = var.quarantine

  dynamic "targets" {
    for_each = var.targets
    content {
      description = targets.value["description"]
      entry_id    = targets.value["entry_id"]
      mac         = targets.value["mac"]

      dynamic "tag" {
        for_each = targets.value.tag
        content {
          tags = tag.value["tags"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_quarantine.this.id
}

output "quarantine" {
  description = "returns a string"
  value       = fortios_switchcontroller_quarantine.this.quarantine
}

output "this" {
  value = fortios_switchcontroller_quarantine.this
}
```

[top](#index)