# fortios_firewall_multicastpolicy

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
module "fortios_firewall_multicastpolicy" {
  source = "./modules/fortios/r/fortios_firewall_multicastpolicy"

  # action - (optional) is a type of string
  action = null
  # auto_asic_offload - (optional) is a type of string
  auto_asic_offload = null
  # comments - (optional) is a type of string
  comments = null
  # dnat - (optional) is a type of string
  dnat = null
  # dstintf - (required) is a type of string
  dstintf = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # end_port - (optional) is a type of number
  end_port = null
  # fosid - (optional) is a type of number
  fosid = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # name - (optional) is a type of string
  name = null
  # protocol - (optional) is a type of number
  protocol = null
  # snat - (optional) is a type of string
  snat = null
  # snat_ip - (optional) is a type of string
  snat_ip = null
  # srcintf - (required) is a type of string
  srcintf = null
  # start_port - (optional) is a type of number
  start_port = null
  # status - (optional) is a type of string
  status = null
  # uuid - (optional) is a type of string
  uuid = null

  dstaddr = [{
    name = null
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

variable "auto_asic_offload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dnat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dstintf" {
  description = "(required)"
  type        = string
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

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "logtraffic" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "snat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snat_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "srcintf" {
  description = "(required)"
  type        = string
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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dstaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "srcaddr" {
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
resource "fortios_firewall_multicastpolicy" "this" {
  # action - (optional) is a type of string
  action = var.action
  # auto_asic_offload - (optional) is a type of string
  auto_asic_offload = var.auto_asic_offload
  # comments - (optional) is a type of string
  comments = var.comments
  # dnat - (optional) is a type of string
  dnat = var.dnat
  # dstintf - (required) is a type of string
  dstintf = var.dstintf
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # end_port - (optional) is a type of number
  end_port = var.end_port
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # logtraffic - (optional) is a type of string
  logtraffic = var.logtraffic
  # name - (optional) is a type of string
  name = var.name
  # protocol - (optional) is a type of number
  protocol = var.protocol
  # snat - (optional) is a type of string
  snat = var.snat
  # snat_ip - (optional) is a type of string
  snat_ip = var.snat_ip
  # srcintf - (required) is a type of string
  srcintf = var.srcintf
  # start_port - (optional) is a type of number
  start_port = var.start_port
  # status - (optional) is a type of string
  status = var.status
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      # name - (optional) is a type of string
      name = dstaddr.value["name"]
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
  value       = fortios_firewall_multicastpolicy.this.action
}

output "auto_asic_offload" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.auto_asic_offload
}

output "dnat" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.dnat
}

output "end_port" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy.this.end_port
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.id
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.logtraffic
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.name
}

output "protocol" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy.this.protocol
}

output "snat" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.snat
}

output "snat_ip" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.snat_ip
}

output "start_port" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy.this.start_port
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.status
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy.this.uuid
}

output "this" {
  value = fortios_firewall_multicastpolicy.this
}
```

[top](#index)