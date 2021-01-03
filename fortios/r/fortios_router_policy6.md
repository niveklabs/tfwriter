# fortios_router_policy6

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
module "fortios_router_policy6" {
  source = "./modules/fortios/r/fortios_router_policy6"

  # comments - (optional) is a type of string
  comments = null
  # dst - (optional) is a type of string
  dst = null
  # end_port - (optional) is a type of number
  end_port = null
  # gateway - (optional) is a type of string
  gateway = null
  # input_device - (required) is a type of string
  input_device = null
  # output_device - (optional) is a type of string
  output_device = null
  # protocol - (optional) is a type of number
  protocol = null
  # seq_num - (optional) is a type of number
  seq_num = null
  # src - (optional) is a type of string
  src = null
  # start_port - (optional) is a type of number
  start_port = null
  # status - (optional) is a type of string
  status = null
  # tos - (optional) is a type of string
  tos = null
  # tos_mask - (optional) is a type of string
  tos_mask = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input_device" {
  description = "(required)"
  type        = string
}

variable "output_device" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = number
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

variable "start_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tos_mask" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_policy6" "this" {
  comments      = var.comments
  dst           = var.dst
  end_port      = var.end_port
  gateway       = var.gateway
  input_device  = var.input_device
  output_device = var.output_device
  protocol      = var.protocol
  seq_num       = var.seq_num
  src           = var.src
  start_port    = var.start_port
  status        = var.status
  tos           = var.tos
  tos_mask      = var.tos_mask
}
```

[top](#index)

### Outputs

```terraform
output "dst" {
  description = "returns a string"
  value       = fortios_router_policy6.this.dst
}

output "end_port" {
  description = "returns a number"
  value       = fortios_router_policy6.this.end_port
}

output "gateway" {
  description = "returns a string"
  value       = fortios_router_policy6.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_router_policy6.this.id
}

output "output_device" {
  description = "returns a string"
  value       = fortios_router_policy6.this.output_device
}

output "protocol" {
  description = "returns a number"
  value       = fortios_router_policy6.this.protocol
}

output "seq_num" {
  description = "returns a number"
  value       = fortios_router_policy6.this.seq_num
}

output "src" {
  description = "returns a string"
  value       = fortios_router_policy6.this.src
}

output "start_port" {
  description = "returns a number"
  value       = fortios_router_policy6.this.start_port
}

output "status" {
  description = "returns a string"
  value       = fortios_router_policy6.this.status
}

output "tos" {
  description = "returns a string"
  value       = fortios_router_policy6.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = fortios_router_policy6.this.tos_mask
}

output "this" {
  value = fortios_router_policy6.this
}
```

[top](#index)