# fortios_router_static6

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
module "fortios_router_static6" {
  source = "./modules/fortios/r/fortios_router_static6"

  # bfd - (optional) is a type of string
  bfd = null
  # blackhole - (optional) is a type of string
  blackhole = null
  # comment - (optional) is a type of string
  comment = null
  # device - (required) is a type of string
  device = null
  # devindex - (optional) is a type of number
  devindex = null
  # distance - (optional) is a type of number
  distance = null
  # dst - (required) is a type of string
  dst = null
  # gateway - (optional) is a type of string
  gateway = null
  # priority - (optional) is a type of number
  priority = null
  # seq_num - (optional) is a type of number
  seq_num = null
  # status - (optional) is a type of string
  status = null
  # virtual_wan_link - (optional) is a type of string
  virtual_wan_link = null
}
```

[top](#index)

### Variables

```terraform
variable "bfd" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "devindex" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "distance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dst" {
  description = "(required)"
  type        = string
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "seq_num" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_wan_link" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_static6" "this" {
  bfd              = var.bfd
  blackhole        = var.blackhole
  comment          = var.comment
  device           = var.device
  devindex         = var.devindex
  distance         = var.distance
  dst              = var.dst
  gateway          = var.gateway
  priority         = var.priority
  seq_num          = var.seq_num
  status           = var.status
  virtual_wan_link = var.virtual_wan_link
}
```

[top](#index)

### Outputs

```terraform
output "bfd" {
  description = "returns a string"
  value       = fortios_router_static6.this.bfd
}

output "blackhole" {
  description = "returns a string"
  value       = fortios_router_static6.this.blackhole
}

output "devindex" {
  description = "returns a number"
  value       = fortios_router_static6.this.devindex
}

output "distance" {
  description = "returns a number"
  value       = fortios_router_static6.this.distance
}

output "gateway" {
  description = "returns a string"
  value       = fortios_router_static6.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_router_static6.this.id
}

output "priority" {
  description = "returns a number"
  value       = fortios_router_static6.this.priority
}

output "seq_num" {
  description = "returns a number"
  value       = fortios_router_static6.this.seq_num
}

output "status" {
  description = "returns a string"
  value       = fortios_router_static6.this.status
}

output "virtual_wan_link" {
  description = "returns a string"
  value       = fortios_router_static6.this.virtual_wan_link
}

output "this" {
  value = fortios_router_static6.this
}
```

[top](#index)