# checkpoint_management_set_ips_update_schedule

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_set_ips_update_schedule" {
  source = "./modules/checkpoint/r/checkpoint_management_set_ips_update_schedule"

  # enabled - (optional) is a type of bool
  enabled = null
  # recurrence - (optional) is a type of map of string
  recurrence = {}
  # time - (optional) is a type of string
  time = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Enable/Disable IPS Update Schedule."
  type        = bool
  default     = null
}

variable "recurrence" {
  description = "(optional) - Days recurrence."
  type        = map(string)
  default     = null
}

variable "time" {
  description = "(optional) - Time in format HH:mm."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_set_ips_update_schedule" "this" {
  enabled    = var.enabled
  recurrence = var.recurrence
  time       = var.time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_set_ips_update_schedule.this.id
}

output "this" {
  value = checkpoint_management_set_ips_update_schedule.this
}
```

[top](#index)