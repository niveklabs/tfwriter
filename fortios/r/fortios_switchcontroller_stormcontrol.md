# fortios_switchcontroller_stormcontrol

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
module "fortios_switchcontroller_stormcontrol" {
  source = "./modules/fortios/r/fortios_switchcontroller_stormcontrol"

  # broadcast - (optional) is a type of string
  broadcast = null
  # rate - (optional) is a type of number
  rate = null
  # unknown_multicast - (optional) is a type of string
  unknown_multicast = null
  # unknown_unicast - (optional) is a type of string
  unknown_unicast = null
}
```

[top](#index)

### Variables

```terraform
variable "broadcast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "unknown_multicast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unknown_unicast" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_stormcontrol" "this" {
  broadcast         = var.broadcast
  rate              = var.rate
  unknown_multicast = var.unknown_multicast
  unknown_unicast   = var.unknown_unicast
}
```

[top](#index)

### Outputs

```terraform
output "broadcast" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrol.this.broadcast
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrol.this.id
}

output "rate" {
  description = "returns a number"
  value       = fortios_switchcontroller_stormcontrol.this.rate
}

output "unknown_multicast" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrol.this.unknown_multicast
}

output "unknown_unicast" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrol.this.unknown_unicast
}

output "this" {
  value = fortios_switchcontroller_stormcontrol.this
}
```

[top](#index)