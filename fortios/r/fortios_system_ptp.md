# fortios_system_ptp

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
module "fortios_system_ptp" {
  source = "./modules/fortios/r/fortios_system_ptp"

  # delay_mechanism - (optional) is a type of string
  delay_mechanism = null
  # interface - (required) is a type of string
  interface = null
  # mode - (optional) is a type of string
  mode = null
  # request_interval - (optional) is a type of number
  request_interval = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "delay_mechanism" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(required)"
  type        = string
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_interval" {
  description = "(optional)"
  type        = number
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
resource "fortios_system_ptp" "this" {
  delay_mechanism  = var.delay_mechanism
  interface        = var.interface
  mode             = var.mode
  request_interval = var.request_interval
  status           = var.status
}
```

[top](#index)

### Outputs

```terraform
output "delay_mechanism" {
  description = "returns a string"
  value       = fortios_system_ptp.this.delay_mechanism
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ptp.this.id
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_ptp.this.mode
}

output "request_interval" {
  description = "returns a number"
  value       = fortios_system_ptp.this.request_interval
}

output "status" {
  description = "returns a string"
  value       = fortios_system_ptp.this.status
}

output "this" {
  value = fortios_system_ptp.this
}
```

[top](#index)