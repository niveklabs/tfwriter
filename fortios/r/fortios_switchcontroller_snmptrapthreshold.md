# fortios_switchcontroller_snmptrapthreshold

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
module "fortios_switchcontroller_snmptrapthreshold" {
  source = "./modules/fortios/r/fortios_switchcontroller_snmptrapthreshold"

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
resource "fortios_switchcontroller_snmptrapthreshold" "this" {
  trap_high_cpu_threshold   = var.trap_high_cpu_threshold
  trap_log_full_threshold   = var.trap_log_full_threshold
  trap_low_memory_threshold = var.trap_low_memory_threshold
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_snmptrapthreshold.this.id
}

output "trap_high_cpu_threshold" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmptrapthreshold.this.trap_high_cpu_threshold
}

output "trap_log_full_threshold" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmptrapthreshold.this.trap_log_full_threshold
}

output "trap_low_memory_threshold" {
  description = "returns a number"
  value       = fortios_switchcontroller_snmptrapthreshold.this.trap_low_memory_threshold
}

output "this" {
  value = fortios_switchcontroller_snmptrapthreshold.this
}
```

[top](#index)