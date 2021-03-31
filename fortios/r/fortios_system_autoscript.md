# fortios_system_autoscript

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
module "fortios_system_autoscript" {
  source = "./modules/fortios/r/fortios_system_autoscript"

  # interval - (optional) is a type of number
  interval = null
  # name - (optional) is a type of string
  name = null
  # output_size - (optional) is a type of number
  output_size = null
  # repeat - (optional) is a type of number
  repeat = null
  # script - (optional) is a type of string
  script = null
  # start - (optional) is a type of string
  start = null
  # timeout - (optional) is a type of number
  timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "repeat" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_autoscript" "this" {
  interval    = var.interval
  name        = var.name
  output_size = var.output_size
  repeat      = var.repeat
  script      = var.script
  start       = var.start
  timeout     = var.timeout
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_autoscript.this.id
}

output "interval" {
  description = "returns a number"
  value       = fortios_system_autoscript.this.interval
}

output "name" {
  description = "returns a string"
  value       = fortios_system_autoscript.this.name
}

output "output_size" {
  description = "returns a number"
  value       = fortios_system_autoscript.this.output_size
}

output "repeat" {
  description = "returns a number"
  value       = fortios_system_autoscript.this.repeat
}

output "start" {
  description = "returns a string"
  value       = fortios_system_autoscript.this.start
}

output "timeout" {
  description = "returns a number"
  value       = fortios_system_autoscript.this.timeout
}

output "this" {
  value = fortios_system_autoscript.this
}
```

[top](#index)