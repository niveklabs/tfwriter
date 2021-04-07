# fortios_switchcontroller_nacdevice

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
module "fortios_switchcontroller_nacdevice" {
  source = "./modules/fortios/r/fortios_switchcontroller_nacdevice"

  # description - (optional) is a type of string
  description = null
  # fosid - (optional) is a type of number
  fosid = null
  # last_known_port - (optional) is a type of string
  last_known_port = null
  # last_known_switch - (optional) is a type of string
  last_known_switch = null
  # last_seen - (optional) is a type of number
  last_seen = null
  # mac - (optional) is a type of string
  mac = null
  # mac_policy - (optional) is a type of string
  mac_policy = null
  # matched_nac_policy - (optional) is a type of string
  matched_nac_policy = null
  # port_policy - (optional) is a type of string
  port_policy = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "last_known_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_known_switch" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_seen" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "matched_nac_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_nacdevice" "this" {
  # description - (optional) is a type of string
  description = var.description
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # last_known_port - (optional) is a type of string
  last_known_port = var.last_known_port
  # last_known_switch - (optional) is a type of string
  last_known_switch = var.last_known_switch
  # last_seen - (optional) is a type of number
  last_seen = var.last_seen
  # mac - (optional) is a type of string
  mac = var.mac
  # mac_policy - (optional) is a type of string
  mac_policy = var.mac_policy
  # matched_nac_policy - (optional) is a type of string
  matched_nac_policy = var.matched_nac_policy
  # port_policy - (optional) is a type of string
  port_policy = var.port_policy
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.description
}

output "fosid" {
  description = "returns a number"
  value       = fortios_switchcontroller_nacdevice.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.id
}

output "last_known_port" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.last_known_port
}

output "last_known_switch" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.last_known_switch
}

output "last_seen" {
  description = "returns a number"
  value       = fortios_switchcontroller_nacdevice.this.last_seen
}

output "mac" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.mac
}

output "mac_policy" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.mac_policy
}

output "matched_nac_policy" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.matched_nac_policy
}

output "port_policy" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.port_policy
}

output "status" {
  description = "returns a string"
  value       = fortios_switchcontroller_nacdevice.this.status
}

output "this" {
  value = fortios_switchcontroller_nacdevice.this
}
```

[top](#index)