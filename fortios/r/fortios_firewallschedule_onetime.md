# fortios_firewallschedule_onetime

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
module "fortios_firewallschedule_onetime" {
  source = "./modules/fortios/r/fortios_firewallschedule_onetime"

  # color - (optional) is a type of number
  color = null
  # end - (required) is a type of string
  end = null
  # expiration_days - (optional) is a type of number
  expiration_days = null
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

variable "end" {
  description = "(required)"
  type        = string
}

variable "expiration_days" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "fortios_firewallschedule_onetime" "this" {
  color           = var.color
  end             = var.end
  expiration_days = var.expiration_days
  name            = var.name
  start           = var.start
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = fortios_firewallschedule_onetime.this.color
}

output "expiration_days" {
  description = "returns a number"
  value       = fortios_firewallschedule_onetime.this.expiration_days
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallschedule_onetime.this.id
}

output "this" {
  value = fortios_firewallschedule_onetime.this
}
```

[top](#index)