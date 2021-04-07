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
    fortios = ">= 1.11.0"
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
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # end_port - (optional) is a type of number
  end_port = null
  # end_source_port - (optional) is a type of number
  end_source_port = null
  # gateway - (optional) is a type of string
  gateway = null
  # input_device_negate - (optional) is a type of string
  input_device_negate = null
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

  internet_service_custom = [{
    name = null
  }]

  internet_service_id = [{
    id = null
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

variable "dynamic_sort_subtable" {
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

variable "input_device_negate" {
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

variable "internet_service_custom" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "internet_service_id" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id = number
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
  # action - (optional) is a type of string
  action = var.action
  # comments - (optional) is a type of string
  comments = var.comments
  # dst_negate - (optional) is a type of string
  dst_negate = var.dst_negate
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # end_port - (optional) is a type of number
  end_port = var.end_port
  # end_source_port - (optional) is a type of number
  end_source_port = var.end_source_port
  # gateway - (optional) is a type of string
  gateway = var.gateway
  # input_device_negate - (optional) is a type of string
  input_device_negate = var.input_device_negate
  # output_device - (optional) is a type of string
  output_device = var.output_device
  # protocol - (optional) is a type of number
  protocol = var.protocol
  # seq_num - (optional) is a type of number
  seq_num = var.seq_num
  # src_negate - (optional) is a type of string
  src_negate = var.src_negate
  # start_port - (optional) is a type of number
  start_port = var.start_port
  # start_source_port - (optional) is a type of number
  start_source_port = var.start_source_port
  # status - (optional) is a type of string
  status = var.status
  # tos - (optional) is a type of string
  tos = var.tos
  # tos_mask - (optional) is a type of string
  tos_mask = var.tos_mask

  dynamic "dst" {
    for_each = var.dst
    content {
      # subnet - (optional) is a type of string
      subnet = dst.value["subnet"]
    }
  }

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      # name - (optional) is a type of string
      name = dstaddr.value["name"]
    }
  }

  dynamic "input_device" {
    for_each = var.input_device
    content {
      # name - (optional) is a type of string
      name = input_device.value["name"]
    }
  }

  dynamic "internet_service_custom" {
    for_each = var.internet_service_custom
    content {
      # name - (optional) is a type of string
      name = internet_service_custom.value["name"]
    }
  }

  dynamic "internet_service_id" {
    for_each = var.internet_service_id
    content {
      # id - (optional) is a type of number
      id = internet_service_id.value["id"]
    }
  }

  dynamic "src" {
    for_each = var.src
    content {
      # subnet - (optional) is a type of string
      subnet = src.value["subnet"]
    }
  }

  dynamic "srcaddr" {
    for_each = var.srcaddr
    content {
      # name - (optional) is a type of string
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

output "input_device_negate" {
  description = "returns a string"
  value       = fortios_router_policy.this.input_device_negate
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