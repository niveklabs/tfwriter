# fortios_firewallschedule_recurring

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
module "fortios_firewallschedule_recurring" {
  source = "./modules/fortios/r/fortios_firewallschedule_recurring"

  # color - (optional) is a type of number
  color = null
  # day - (optional) is a type of string
  day = null
  # end - (required) is a type of string
  end = null
  # name - (required) is a type of string
  name = null
  # start - (required) is a type of string
  start = null
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

variable "day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "start" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallschedule_recurring" "this" {
  # color - (optional) is a type of number
  color = var.color
  # day - (optional) is a type of string
  day = var.day
  # end - (required) is a type of string
  end = var.end
  # name - (required) is a type of string
  name = var.name
  # start - (required) is a type of string
  start = var.start
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = fortios_firewallschedule_recurring.this.color
}

output "day" {
  description = "returns a string"
  value       = fortios_firewallschedule_recurring.this.day
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallschedule_recurring.this.id
}

output "this" {
  value = fortios_firewallschedule_recurring.this
}
```

[top](#index)