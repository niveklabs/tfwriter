# fortios_switchcontrollerautoconfig_policy

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
module "fortios_switchcontrollerautoconfig_policy" {
  source = "./modules/fortios/r/fortios_switchcontrollerautoconfig_policy"

  # igmp_flood_report - (optional) is a type of string
  igmp_flood_report = null
  # igmp_flood_traffic - (optional) is a type of string
  igmp_flood_traffic = null
  # name - (required) is a type of string
  name = null
  # poe_status - (optional) is a type of string
  poe_status = null
  # qos_policy - (optional) is a type of string
  qos_policy = null
  # storm_control_policy - (optional) is a type of string
  storm_control_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "igmp_flood_report" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "igmp_flood_traffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "poe_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storm_control_policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerautoconfig_policy" "this" {
  # igmp_flood_report - (optional) is a type of string
  igmp_flood_report = var.igmp_flood_report
  # igmp_flood_traffic - (optional) is a type of string
  igmp_flood_traffic = var.igmp_flood_traffic
  # name - (required) is a type of string
  name = var.name
  # poe_status - (optional) is a type of string
  poe_status = var.poe_status
  # qos_policy - (optional) is a type of string
  qos_policy = var.qos_policy
  # storm_control_policy - (optional) is a type of string
  storm_control_policy = var.storm_control_policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.id
}

output "igmp_flood_report" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.igmp_flood_report
}

output "igmp_flood_traffic" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.igmp_flood_traffic
}

output "poe_status" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.poe_status
}

output "qos_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.qos_policy
}

output "storm_control_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_policy.this.storm_control_policy
}

output "this" {
  value = fortios_switchcontrollerautoconfig_policy.this
}
```

[top](#index)