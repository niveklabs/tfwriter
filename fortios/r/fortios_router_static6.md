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
    fortios = ">= 1.11.0"
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
  # dst - (optional) is a type of string
  dst = null
  # gateway - (optional) is a type of string
  gateway = null
  # link_monitor_exempt - (optional) is a type of string
  link_monitor_exempt = null
  # priority - (optional) is a type of number
  priority = null
  # sdwan - (optional) is a type of string
  sdwan = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_monitor_exempt" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sdwan" {
  description = "(optional)"
  type        = string
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
  # bfd - (optional) is a type of string
  bfd = var.bfd
  # blackhole - (optional) is a type of string
  blackhole = var.blackhole
  # comment - (optional) is a type of string
  comment = var.comment
  # device - (required) is a type of string
  device = var.device
  # devindex - (optional) is a type of number
  devindex = var.devindex
  # distance - (optional) is a type of number
  distance = var.distance
  # dst - (optional) is a type of string
  dst = var.dst
  # gateway - (optional) is a type of string
  gateway = var.gateway
  # link_monitor_exempt - (optional) is a type of string
  link_monitor_exempt = var.link_monitor_exempt
  # priority - (optional) is a type of number
  priority = var.priority
  # sdwan - (optional) is a type of string
  sdwan = var.sdwan
  # seq_num - (optional) is a type of number
  seq_num = var.seq_num
  # status - (optional) is a type of string
  status = var.status
  # virtual_wan_link - (optional) is a type of string
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

output "dst" {
  description = "returns a string"
  value       = fortios_router_static6.this.dst
}

output "gateway" {
  description = "returns a string"
  value       = fortios_router_static6.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_router_static6.this.id
}

output "link_monitor_exempt" {
  description = "returns a string"
  value       = fortios_router_static6.this.link_monitor_exempt
}

output "priority" {
  description = "returns a number"
  value       = fortios_router_static6.this.priority
}

output "sdwan" {
  description = "returns a string"
  value       = fortios_router_static6.this.sdwan
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