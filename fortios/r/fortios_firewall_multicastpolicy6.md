# fortios_firewall_multicastpolicy6

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
module "fortios_firewall_multicastpolicy6" {
  source = "./modules/fortios/r/fortios_firewall_multicastpolicy6"

  # action - (optional) is a type of string
  action = null
  # dstintf - (required) is a type of string
  dstintf = null
  # end_port - (optional) is a type of number
  end_port = null
  # fosid - (optional) is a type of number
  fosid = null
  # logtraffic - (optional) is a type of string
  logtraffic = null
  # protocol - (optional) is a type of number
  protocol = null
  # srcintf - (required) is a type of string
  srcintf = null
  # start_port - (optional) is a type of number
  start_port = null
  # status - (optional) is a type of string
  status = null

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

variable "dstintf" {
  description = "(required)"
  type        = string
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

variable "protocol" {
  description = "(optional)"
  type        = number
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
resource "fortios_firewall_multicastpolicy6" "this" {
  action     = var.action
  dstintf    = var.dstintf
  end_port   = var.end_port
  fosid      = var.fosid
  logtraffic = var.logtraffic
  protocol   = var.protocol
  srcintf    = var.srcintf
  start_port = var.start_port
  status     = var.status

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
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
  value       = fortios_firewall_multicastpolicy6.this.action
}

output "end_port" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy6.this.end_port
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy6.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy6.this.id
}

output "logtraffic" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy6.this.logtraffic
}

output "protocol" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy6.this.protocol
}

output "start_port" {
  description = "returns a number"
  value       = fortios_firewall_multicastpolicy6.this.start_port
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_multicastpolicy6.this.status
}

output "this" {
  value = fortios_firewall_multicastpolicy6.this
}
```

[top](#index)