# fortios_system_automationtrigger

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
module "fortios_system_automationtrigger" {
  source = "./modules/fortios/r/fortios_system_automationtrigger"

  # event_type - (optional) is a type of string
  event_type = null
  # ioc_level - (optional) is a type of string
  ioc_level = null
  # license_type - (optional) is a type of string
  license_type = null
  # logid - (optional) is a type of number
  logid = null
  # name - (optional) is a type of string
  name = null
  # trigger_day - (optional) is a type of number
  trigger_day = null
  # trigger_frequency - (optional) is a type of string
  trigger_frequency = null
  # trigger_hour - (optional) is a type of number
  trigger_hour = null
  # trigger_minute - (optional) is a type of number
  trigger_minute = null
  # trigger_type - (optional) is a type of string
  trigger_type = null
  # trigger_weekday - (optional) is a type of string
  trigger_weekday = null
}
```

[top](#index)

### Variables

```terraform
variable "event_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ioc_level" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trigger_day" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trigger_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trigger_hour" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trigger_minute" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trigger_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trigger_weekday" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_automationtrigger" "this" {
  event_type        = var.event_type
  ioc_level         = var.ioc_level
  license_type      = var.license_type
  logid             = var.logid
  name              = var.name
  trigger_day       = var.trigger_day
  trigger_frequency = var.trigger_frequency
  trigger_hour      = var.trigger_hour
  trigger_minute    = var.trigger_minute
  trigger_type      = var.trigger_type
  trigger_weekday   = var.trigger_weekday
}
```

[top](#index)

### Outputs

```terraform
output "event_type" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.event_type
}

output "id" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.id
}

output "ioc_level" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.ioc_level
}

output "license_type" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.license_type
}

output "logid" {
  description = "returns a number"
  value       = fortios_system_automationtrigger.this.logid
}

output "name" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.name
}

output "trigger_day" {
  description = "returns a number"
  value       = fortios_system_automationtrigger.this.trigger_day
}

output "trigger_frequency" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.trigger_frequency
}

output "trigger_hour" {
  description = "returns a number"
  value       = fortios_system_automationtrigger.this.trigger_hour
}

output "trigger_minute" {
  description = "returns a number"
  value       = fortios_system_automationtrigger.this.trigger_minute
}

output "trigger_type" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.trigger_type
}

output "trigger_weekday" {
  description = "returns a string"
  value       = fortios_system_automationtrigger.this.trigger_weekday
}

output "this" {
  value = fortios_system_automationtrigger.this
}
```

[top](#index)