# fortios_switchcontroller_stormcontrolpolicy

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
module "fortios_switchcontroller_stormcontrolpolicy" {
  source = "./modules/fortios/r/fortios_switchcontroller_stormcontrolpolicy"

  # broadcast - (optional) is a type of string
  broadcast = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # rate - (optional) is a type of number
  rate = null
  # storm_control_mode - (optional) is a type of string
  storm_control_mode = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "storm_control_mode" {
  description = "(optional)"
  type        = string
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
resource "fortios_switchcontroller_stormcontrolpolicy" "this" {
  # broadcast - (optional) is a type of string
  broadcast = var.broadcast
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # rate - (optional) is a type of number
  rate = var.rate
  # storm_control_mode - (optional) is a type of string
  storm_control_mode = var.storm_control_mode
  # unknown_multicast - (optional) is a type of string
  unknown_multicast = var.unknown_multicast
  # unknown_unicast - (optional) is a type of string
  unknown_unicast = var.unknown_unicast
}
```

[top](#index)

### Outputs

```terraform
output "broadcast" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.broadcast
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.name
}

output "rate" {
  description = "returns a number"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.rate
}

output "storm_control_mode" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.storm_control_mode
}

output "unknown_multicast" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.unknown_multicast
}

output "unknown_unicast" {
  description = "returns a string"
  value       = fortios_switchcontroller_stormcontrolpolicy.this.unknown_unicast
}

output "this" {
  value = fortios_switchcontroller_stormcontrolpolicy.this
}
```

[top](#index)