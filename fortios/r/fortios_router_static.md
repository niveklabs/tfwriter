# fortios_router_static

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
module "fortios_router_static" {
  source = "./modules/fortios/r/fortios_router_static"

  # bfd - (optional) is a type of string
  bfd = null
  # blackhole - (optional) is a type of string
  blackhole = null
  # comment - (optional) is a type of string
  comment = null
  # device - (optional) is a type of string
  device = null
  # distance - (optional) is a type of number
  distance = null
  # dst - (optional) is a type of string
  dst = null
  # dstaddr - (optional) is a type of string
  dstaddr = null
  # dynamic_gateway - (optional) is a type of string
  dynamic_gateway = null
  # gateway - (optional) is a type of string
  gateway = null
  # internet_service - (optional) is a type of number
  internet_service = null
  # internet_service_custom - (optional) is a type of string
  internet_service_custom = null
  # link_monitor_exempt - (optional) is a type of string
  link_monitor_exempt = null
  # priority - (optional) is a type of number
  priority = null
  # sdwan - (optional) is a type of string
  sdwan = null
  # seq_num - (optional) is a type of number
  seq_num = null
  # src - (optional) is a type of string
  src = null
  # status - (optional) is a type of string
  status = null
  # virtual_wan_link - (optional) is a type of string
  virtual_wan_link = null
  # vrf - (optional) is a type of number
  vrf = null
  # weight - (optional) is a type of number
  weight = null
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
  description = "(optional)"
  type        = string
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

variable "dstaddr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_service" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internet_service_custom" {
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

variable "src" {
  description = "(optional)"
  type        = string
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

variable "vrf" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_static" "this" {
  bfd                     = var.bfd
  blackhole               = var.blackhole
  comment                 = var.comment
  device                  = var.device
  distance                = var.distance
  dst                     = var.dst
  dstaddr                 = var.dstaddr
  dynamic_gateway         = var.dynamic_gateway
  gateway                 = var.gateway
  internet_service        = var.internet_service
  internet_service_custom = var.internet_service_custom
  link_monitor_exempt     = var.link_monitor_exempt
  priority                = var.priority
  sdwan                   = var.sdwan
  seq_num                 = var.seq_num
  src                     = var.src
  status                  = var.status
  virtual_wan_link        = var.virtual_wan_link
  vrf                     = var.vrf
  weight                  = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "bfd" {
  description = "returns a string"
  value       = fortios_router_static.this.bfd
}

output "blackhole" {
  description = "returns a string"
  value       = fortios_router_static.this.blackhole
}

output "device" {
  description = "returns a string"
  value       = fortios_router_static.this.device
}

output "distance" {
  description = "returns a number"
  value       = fortios_router_static.this.distance
}

output "dst" {
  description = "returns a string"
  value       = fortios_router_static.this.dst
}

output "dstaddr" {
  description = "returns a string"
  value       = fortios_router_static.this.dstaddr
}

output "dynamic_gateway" {
  description = "returns a string"
  value       = fortios_router_static.this.dynamic_gateway
}

output "gateway" {
  description = "returns a string"
  value       = fortios_router_static.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_router_static.this.id
}

output "internet_service" {
  description = "returns a number"
  value       = fortios_router_static.this.internet_service
}

output "internet_service_custom" {
  description = "returns a string"
  value       = fortios_router_static.this.internet_service_custom
}

output "link_monitor_exempt" {
  description = "returns a string"
  value       = fortios_router_static.this.link_monitor_exempt
}

output "priority" {
  description = "returns a number"
  value       = fortios_router_static.this.priority
}

output "sdwan" {
  description = "returns a string"
  value       = fortios_router_static.this.sdwan
}

output "seq_num" {
  description = "returns a number"
  value       = fortios_router_static.this.seq_num
}

output "src" {
  description = "returns a string"
  value       = fortios_router_static.this.src
}

output "status" {
  description = "returns a string"
  value       = fortios_router_static.this.status
}

output "virtual_wan_link" {
  description = "returns a string"
  value       = fortios_router_static.this.virtual_wan_link
}

output "vrf" {
  description = "returns a number"
  value       = fortios_router_static.this.vrf
}

output "weight" {
  description = "returns a number"
  value       = fortios_router_static.this.weight
}

output "this" {
  value = fortios_router_static.this
}
```

[top](#index)