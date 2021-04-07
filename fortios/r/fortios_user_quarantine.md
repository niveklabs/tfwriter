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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_quarantine" {
  source = "./modules/fortios/r/fortios_user_quarantine"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # firewall_groups - (optional) is a type of string
  firewall_groups = null
  # quarantine - (optional) is a type of string
  quarantine = null
  # traffic_policy - (optional) is a type of string
  traffic_policy = null

  targets = [{
    description = null
    entry       = null
    macs = [{
      description = null
      drop        = null
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
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_groups" {
  description = "(optional)"
  type        = string
  default     = null
}

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
          drop        = string
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
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # firewall_groups - (optional) is a type of string
  firewall_groups = var.firewall_groups
  # quarantine - (optional) is a type of string
  quarantine = var.quarantine
  # traffic_policy - (optional) is a type of string
  traffic_policy = var.traffic_policy

  dynamic "targets" {
    for_each = var.targets
    content {
      # description - (optional) is a type of string
      description = targets.value["description"]
      # entry - (optional) is a type of string
      entry = targets.value["entry"]

      dynamic "macs" {
        for_each = targets.value.macs
        content {
          # description - (optional) is a type of string
          description = macs.value["description"]
          # drop - (optional) is a type of string
          drop = macs.value["drop"]
          # entry_id - (optional) is a type of number
          entry_id = macs.value["entry_id"]
          # mac - (optional) is a type of string
          mac = macs.value["mac"]
          # parent - (optional) is a type of string
          parent = macs.value["parent"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "firewall_groups" {
  description = "returns a string"
  value       = fortios_user_quarantine.this.firewall_groups
}

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