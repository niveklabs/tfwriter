# fortios_systemautoupdate_schedule

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
module "fortios_systemautoupdate_schedule" {
  source = "./modules/fortios/r/fortios_systemautoupdate_schedule"

  # day - (optional) is a type of string
  day = null
  # frequency - (required) is a type of string
  frequency = null
  # status - (required) is a type of string
  status = null
  # time - (required) is a type of string
  time = null
}
```

[top](#index)

### Variables

```terraform
variable "day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "frequency" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "time" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemautoupdate_schedule" "this" {
  # day - (optional) is a type of string
  day = var.day
  # frequency - (required) is a type of string
  frequency = var.frequency
  # status - (required) is a type of string
  status = var.status
  # time - (required) is a type of string
  time = var.time
}
```

[top](#index)

### Outputs

```terraform
output "day" {
  description = "returns a string"
  value       = fortios_systemautoupdate_schedule.this.day
}

output "id" {
  description = "returns a string"
  value       = fortios_systemautoupdate_schedule.this.id
}

output "this" {
  value = fortios_systemautoupdate_schedule.this
}
```

[top](#index)