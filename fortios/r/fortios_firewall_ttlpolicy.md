# fortios_firewall_ttlpolicy

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
module "fortios_firewall_ttlpolicy" {
  source = "./modules/fortios/r/fortios_firewall_ttlpolicy"

  # action - (optional) is a type of string
  action = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # fosid - (required) is a type of number
  fosid = null
  # schedule - (required) is a type of string
  schedule = null
  # srcintf - (required) is a type of string
  srcintf = null
  # status - (optional) is a type of string
  status = null
  # ttl - (required) is a type of string
  ttl = null

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

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(required)"
  type        = number
}

variable "schedule" {
  description = "(required)"
  type        = string
}

variable "srcintf" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(required)"
  type        = string
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
resource "fortios_firewall_ttlpolicy" "this" {
  # action - (optional) is a type of string
  action = var.action
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # fosid - (required) is a type of number
  fosid = var.fosid
  # schedule - (required) is a type of string
  schedule = var.schedule
  # srcintf - (required) is a type of string
  srcintf = var.srcintf
  # status - (optional) is a type of string
  status = var.status
  # ttl - (required) is a type of string
  ttl = var.ttl

  dynamic "service" {
    for_each = var.service
    content {
      # name - (optional) is a type of string
      name = service.value["name"]
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
  value       = fortios_firewall_ttlpolicy.this.action
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_ttlpolicy.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_firewall_ttlpolicy.this.status
}

output "this" {
  value = fortios_firewall_ttlpolicy.this
}
```

[top](#index)