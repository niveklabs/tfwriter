# fortios_firewall_centralsnatmap

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
module "fortios_firewall_centralsnatmap" {
  source = "./modules/fortios/r/fortios_firewall_centralsnatmap"

  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # nat - (required) is a type of string
  nat = null
  # nat_port - (optional) is a type of string
  nat_port = null
  # orig_port - (required) is a type of string
  orig_port = null
  # policyid - (optional) is a type of number
  policyid = null
  # protocol - (required) is a type of number
  protocol = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  dst_addr = [{
    name = null
  }]

  dst_addr6 = [{
    name = null
  }]

  dstintf = [{
    name = null
  }]

  nat_ippool = [{
    name = null
  }]

  nat_ippool6 = [{
    name = null
  }]

  orig_addr = [{
    name = null
  }]

  orig_addr6 = [{
    name = null
  }]

  srcintf = [{
    name = null
  }]
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

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat" {
  description = "(required)"
  type        = string
}

variable "nat_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "orig_port" {
  description = "(required)"
  type        = string
}

variable "policyid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(required)"
  type        = number
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_addr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "dst_addr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "dstintf" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "nat_ippool" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "nat_ippool6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "orig_addr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "orig_addr6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}

variable "srcintf" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_centralsnatmap" "this" {
  comments              = var.comments
  dynamic_sort_subtable = var.dynamic_sort_subtable
  nat                   = var.nat
  nat_port              = var.nat_port
  orig_port             = var.orig_port
  policyid              = var.policyid
  protocol              = var.protocol
  status                = var.status
  type                  = var.type
  uuid                  = var.uuid

  dynamic "dst_addr" {
    for_each = var.dst_addr
    content {
      name = dst_addr.value["name"]
    }
  }

  dynamic "dst_addr6" {
    for_each = var.dst_addr6
    content {
      name = dst_addr6.value["name"]
    }
  }

  dynamic "dstintf" {
    for_each = var.dstintf
    content {
      name = dstintf.value["name"]
    }
  }

  dynamic "nat_ippool" {
    for_each = var.nat_ippool
    content {
      name = nat_ippool.value["name"]
    }
  }

  dynamic "nat_ippool6" {
    for_each = var.nat_ippool6
    content {
      name = nat_ippool6.value["name"]
    }
  }

  dynamic "orig_addr" {
    for_each = var.orig_addr
    content {
      name = orig_addr.value["name"]
    }
  }

  dynamic "orig_addr6" {
    for_each = var.orig_addr6
    content {
      name = orig_addr6.value["name"]
    }
  }

  dynamic "srcintf" {
    for_each = var.srcintf
    content {
      name = srcintf.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_firewall_centralsnatmap.this.id
}

output "nat_port" {
  description = "returns a string"
  value       = fortios_firewall_centralsnatmap.this.nat_port
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_centralsnatmap.this.policyid
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_centralsnatmap.this.status
}

output "type" {
  description = "returns a string"
  value       = fortios_firewall_centralsnatmap.this.type
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_centralsnatmap.this.uuid
}

output "this" {
  value = fortios_firewall_centralsnatmap.this
}
```

[top](#index)