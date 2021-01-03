# fortios_user_quarantine

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
module "fortios_user_quarantine" {
  source = "./modules/fortios/r/fortios_user_quarantine"

  # quarantine - (optional) is a type of string
  quarantine = null
  # traffic_policy - (optional) is a type of string
  traffic_policy = null

  targets = [{
    description = null
    entry       = null
    macs = [{
      description = null
      entry_id    = null
      mac         = null
      parent      = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "quarantine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "targets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      entry       = string
      macs = list(object(
        {
          description = string
          entry_id    = number
          mac         = string
          parent      = string
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
resource "fortios_user_quarantine" "this" {
  quarantine     = var.quarantine
  traffic_policy = var.traffic_policy

  dynamic "targets" {
    for_each = var.targets
    content {
      description = targets.value["description"]
      entry       = targets.value["entry"]

      dynamic "macs" {
        for_each = targets.value.macs
        content {
          description = macs.value["description"]
          entry_id    = macs.value["entry_id"]
          mac         = macs.value["mac"]
          parent      = macs.value["parent"]
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
  value       = fortios_user_quarantine.this.id
}

output "quarantine" {
  description = "returns a string"
  value       = fortios_user_quarantine.this.quarantine
}

output "traffic_policy" {
  description = "returns a string"
  value       = fortios_user_quarantine.this.traffic_policy
}

output "this" {
  value = fortios_user_quarantine.this
}
```

[top](#index)