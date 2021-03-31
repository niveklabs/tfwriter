# fortios_firewall_localinpolicy6

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
module "fortios_firewall_localinpolicy6" {
  source = "./modules/fortios/r/fortios_firewall_localinpolicy6"

  # action - (optional) is a type of string
  action = null
  # comments - (optional) is a type of string
  comments = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # intf - (required) is a type of string
  intf = null
  # policyid - (optional) is a type of number
  policyid = null
  # schedule - (required) is a type of string
  schedule = null
  # status - (optional) is a type of string
  status = null
  # uuid - (optional) is a type of string
  uuid = null

  dstaddr = [{
    name = null
  }]

  service = [{
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

variable "intf" {
  description = "(required)"
  type        = string
}

variable "policyid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "schedule" {
  description = "(required)"
  type        = string
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

variable "service" {
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
resource "fortios_firewall_localinpolicy6" "this" {
  action                = var.action
  comments              = var.comments
  dynamic_sort_subtable = var.dynamic_sort_subtable
  intf                  = var.intf
  policyid              = var.policyid
  schedule              = var.schedule
  status                = var.status
  uuid                  = var.uuid

  dynamic "dstaddr" {
    for_each = var.dstaddr
    content {
      name = dstaddr.value["name"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      name = service.value["name"]
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
  value       = fortios_firewall_localinpolicy6.this.action
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy6.this.id
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_localinpolicy6.this.policyid
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy6.this.status
}

output "uuid" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy6.this.uuid
}

output "this" {
  value = fortios_firewall_localinpolicy6.this
}
```

[top](#index)