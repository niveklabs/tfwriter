# fortios_networking_route_static

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
module "fortios_networking_route_static" {
  source = "./modules/fortios/r/fortios_networking_route_static"

  # blackhole - (optional) is a type of string
  blackhole = null
  # comment - (optional) is a type of string
  comment = null
  # device - (required) is a type of string
  device = null
  # distance - (optional) is a type of string
  distance = null
  # dst - (optional) is a type of string
  dst = null
  # gateway - (required) is a type of string
  gateway = null
  # internet_service - (optional) is a type of number
  internet_service = null
  # priority - (optional) is a type of string
  priority = null
  # status - (optional) is a type of string
  status = null
  # weight - (optional) is a type of string
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "blackhole" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device" {
  description = "(required)"
  type        = string
}

variable "distance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(required)"
  type        = string
}

variable "internet_service" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_networking_route_static" "this" {
  blackhole        = var.blackhole
  comment          = var.comment
  device           = var.device
  distance         = var.distance
  dst              = var.dst
  gateway          = var.gateway
  internet_service = var.internet_service
  priority         = var.priority
  status           = var.status
  weight           = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "blackhole" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.blackhole
}

output "distance" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.distance
}

output "dst" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.dst
}

output "id" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.id
}

output "internet_service" {
  description = "returns a number"
  value       = fortios_networking_route_static.this.internet_service
}

output "priority" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.priority
}

output "status" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.status
}

output "weight" {
  description = "returns a string"
  value       = fortios_networking_route_static.this.weight
}

output "this" {
  value = fortios_networking_route_static.this
}
```

[top](#index)