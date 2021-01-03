# fortios_router_policy

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
module "fortios_router_policy" {
  source = "./modules/fortios/r/fortios_router_policy"

  # action - (optional) is a type of string
  action = null
  # comments - (optional) is a type of string
  comments = null
  # dst_negate - (optional) is a type of string
  dst_negate = null
  # end_port - (optional) is a type of number
  end_port = null
  # end_source_port - (optional) is a type of number
  end_source_port = null
  # gateway - (optional) is a type of string
  gateway = null
  # output_device - (optional) is a type of string
  output_device = null
  # protocol - (optional) is a type of number
  protocol = null
  # seq_num - (optional) is a type of number
  seq_num = null
  # src_negate - (optional) is a type of string
  src_negate = null
  # start_port - (optional) is a type of number
  start_port = null
  # start_source_port - (optional) is a type of number
  start_source_port = null
  # status - (optional) is a type of string
  status = null
  # tos - (optional) is a type of string
  tos = null
  # tos_mask - (optional) is a type of string
  tos_mask = null

  dst = [{
    subnet = null
  }]

  dstaddr = [{
    name = null
  }]

  input_device = [{
    name = null
  }]

  src = [{
    subnet = null
  }]

  srcaddr = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "end_source_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "gateway" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "src_negate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "start_source_port" {
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

variable "dst" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      subnet = string
    }
  ))
  default = []
}

variable "dstaddr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "input_device" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "src" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      subnet = string
    }
  ))
  default = []
}

variable "srcaddr" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_policy" "this" {
  action            = var.action
  comments          = var.comments
  dst_negate        = var.dst_negate
  end_port          = var.end_port
  end_source_port   = var.end_source_port
  gateway           = var.gateway
  output_device     = var.output_device
  protocol          = var.protocol
  seq_num           = var.seq_num
  src_negate        = var.src_negate
  start_port        = var.start_port
  start_source_port = var.start_source_port
  status            = var.status
  tos               = var.tos
  tos_mask          = var.tos_mask

  dynamic "dst" {
    for_each = var.dst
    content {
      subnet = dst.value["subnet"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
    }
  }

  dynamic "input_device" {
    for_each = var.input_device
    content {
      name = input_device.value["name"]
    }
  }

  dynamic "src" {
    for_each = var.src
    content {
      subnet = src.value["subnet"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      name = srcaddr.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = fortios_router_policy.this.action
}

output "dst_negate" {
  description = "returns a string"
  value       = fortios_router_policy.this.dst_negate
}

output "end_port" {
  description = "returns a number"
  value       = fortios_router_policy.this.end_port
}

output "end_source_port" {
  description = "returns a number"
  value       = fortios_router_policy.this.end_source_port
}

output "gateway" {
  description = "returns a string"
  value       = fortios_router_policy.this.gateway
}

output "id" {
  description = "returns a string"
  value       = fortios_router_policy.this.id
}

output "output_device" {
  description = "returns a string"
  value       = fortios_router_policy.this.output_device
}

output "protocol" {
  description = "returns a number"
  value       = fortios_router_policy.this.protocol
}

output "seq_num" {
  description = "returns a number"
  value       = fortios_router_policy.this.seq_num
}

output "src_negate" {
  description = "returns a string"
  value       = fortios_router_policy.this.src_negate
}

output "start_port" {
  description = "returns a number"
  value       = fortios_router_policy.this.start_port
}

output "start_source_port" {
  description = "returns a number"
  value       = fortios_router_policy.this.start_source_port
}

output "status" {
  description = "returns a string"
  value       = fortios_router_policy.this.status
}

output "tos" {
  description = "returns a string"
  value       = fortios_router_policy.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = fortios_router_policy.this.tos_mask
}

output "this" {
  value = fortios_router_policy.this
}
```

[top](#index)