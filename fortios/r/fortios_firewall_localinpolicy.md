# fortios_firewall_localinpolicy

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
module "fortios_firewall_localinpolicy" {
  source = "./modules/fortios/r/fortios_firewall_localinpolicy"

  # action - (optional) is a type of string
  action = null
  # comments - (optional) is a type of string
  comments = null
  # ha_mgmt_intf_only - (optional) is a type of string
  ha_mgmt_intf_only = null
  # intf - (optional) is a type of string
  intf = null
  # policyid - (optional) is a type of number
  policyid = null
  # schedule - (required) is a type of string
  schedule = null
  # status - (optional) is a type of string
  status = null

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

variable "ha_mgmt_intf_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "intf" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "dstaddr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
}

variable "service" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
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
resource "fortios_firewall_localinpolicy" "this" {
  action            = var.action
  comments          = var.comments
  ha_mgmt_intf_only = var.ha_mgmt_intf_only
  intf              = var.intf
  policyid          = var.policyid
  schedule          = var.schedule
  status            = var.status

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
  value       = fortios_firewall_localinpolicy.this.action
}

output "ha_mgmt_intf_only" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy.this.ha_mgmt_intf_only
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy.this.id
}

output "intf" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy.this.intf
}

output "policyid" {
  description = "returns a number"
  value       = fortios_firewall_localinpolicy.this.policyid
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_localinpolicy.this.status
}

output "this" {
  value = fortios_firewall_localinpolicy.this
}
```

[top](#index)