# fortios_system_storage

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
module "fortios_system_storage" {
  source = "./modules/fortios/r/fortios_system_storage"

  # device - (optional) is a type of string
  device = null
  # media_status - (optional) is a type of string
  media_status = null
  # name - (optional) is a type of string
  name = null
  # order - (optional) is a type of number
  order = null
  # partition - (optional) is a type of string
  partition = null
  # size - (optional) is a type of number
  size = null
  # status - (optional) is a type of string
  status = null
  # usage - (optional) is a type of string
  usage = null
  # wanopt_mode - (optional) is a type of string
  wanopt_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "media_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "order" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "partition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "usage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wanopt_mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_storage" "this" {
  device       = var.device
  media_status = var.media_status
  name         = var.name
  order        = var.order
  partition    = var.partition
  size         = var.size
  status       = var.status
  usage        = var.usage
  wanopt_mode  = var.wanopt_mode
}
```

[top](#index)

### Outputs

```terraform
output "device" {
  description = "returns a string"
  value       = fortios_system_storage.this.device
}

output "id" {
  description = "returns a string"
  value       = fortios_system_storage.this.id
}

output "media_status" {
  description = "returns a string"
  value       = fortios_system_storage.this.media_status
}

output "name" {
  description = "returns a string"
  value       = fortios_system_storage.this.name
}

output "order" {
  description = "returns a number"
  value       = fortios_system_storage.this.order
}

output "partition" {
  description = "returns a string"
  value       = fortios_system_storage.this.partition
}

output "size" {
  description = "returns a number"
  value       = fortios_system_storage.this.size
}

output "status" {
  description = "returns a string"
  value       = fortios_system_storage.this.status
}

output "usage" {
  description = "returns a string"
  value       = fortios_system_storage.this.usage
}

output "wanopt_mode" {
  description = "returns a string"
  value       = fortios_system_storage.this.wanopt_mode
}

output "this" {
  value = fortios_system_storage.this
}
```

[top](#index)