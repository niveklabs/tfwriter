# fortios_systemsnmp_sysinfo

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
module "fortios_systemsnmp_sysinfo" {
  source = "./modules/fortios/r/fortios_systemsnmp_sysinfo"

  # contact_info - (optional) is a type of string
  contact_info = null
  # description - (optional) is a type of string
  description = null
  # engine_id - (optional) is a type of string
  engine_id = null
  # location - (optional) is a type of string
  location = null
  # status - (optional) is a type of string
  status = null
  # trap_high_cpu_threshold - (optional) is a type of number
  trap_high_cpu_threshold = null
  # trap_log_full_threshold - (optional) is a type of number
  trap_log_full_threshold = null
  # trap_low_memory_threshold - (optional) is a type of number
  trap_low_memory_threshold = null
}
```

[top](#index)

### Variables

```terraform
variable "contact_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trap_high_cpu_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_log_full_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "trap_low_memory_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_systemsnmp_sysinfo" "this" {
  contact_info              = var.contact_info
  description               = var.description
  engine_id                 = var.engine_id
  location                  = var.location
  status                    = var.status
  trap_high_cpu_threshold   = var.trap_high_cpu_threshold
  trap_log_full_threshold   = var.trap_log_full_threshold
  trap_low_memory_threshold = var.trap_low_memory_threshold
}
```

[top](#index)

### Outputs

```terraform
output "engine_id" {
  description = "returns a string"
  value       = fortios_systemsnmp_sysinfo.this.engine_id
}

output "id" {
  description = "returns a string"
  value       = fortios_systemsnmp_sysinfo.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_systemsnmp_sysinfo.this.status
}

output "trap_high_cpu_threshold" {
  description = "returns a number"
  value       = fortios_systemsnmp_sysinfo.this.trap_high_cpu_threshold
}

output "trap_log_full_threshold" {
  description = "returns a number"
  value       = fortios_systemsnmp_sysinfo.this.trap_log_full_threshold
}

output "trap_low_memory_threshold" {
  description = "returns a number"
  value       = fortios_systemsnmp_sysinfo.this.trap_low_memory_threshold
}

output "this" {
  value = fortios_systemsnmp_sysinfo.this
}
```

[top](#index)