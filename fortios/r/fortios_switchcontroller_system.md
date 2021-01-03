# fortios_switchcontroller_system

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
module "fortios_switchcontroller_system" {
  source = "./modules/fortios/r/fortios_switchcontroller_system"

  # parallel_process - (optional) is a type of number
  parallel_process = null
  # parallel_process_override - (optional) is a type of string
  parallel_process_override = null
}
```

[top](#index)

### Variables

```terraform
variable "parallel_process" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "parallel_process_override" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_system" "this" {
  parallel_process          = var.parallel_process
  parallel_process_override = var.parallel_process_override
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_system.this.id
}

output "parallel_process" {
  description = "returns a number"
  value       = fortios_switchcontroller_system.this.parallel_process
}

output "parallel_process_override" {
  description = "returns a string"
  value       = fortios_switchcontroller_system.this.parallel_process_override
}

output "this" {
  value = fortios_switchcontroller_system.this
}
```

[top](#index)