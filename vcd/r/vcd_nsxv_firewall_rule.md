# vcd_nsxv_firewall_rule

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_nsxv_firewall_rule" {
  source = [{
    exclude            = null
    gateway_interfaces = []
    ip_addresses       = []
    ip_sets            = []
    org_networks       = []
    vm_ids             = []
  }]

  # above_rule_id - (optional) is a type of string
  above_rule_id = null
  # action - (optional) is a type of string
  action = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # enabled - (optional) is a type of bool
  enabled = null
  # logging_enabled - (optional) is a type of bool
  logging_enabled = null
  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # rule_tag - (optional) is a type of number
  rule_tag = null
  # rule_type - (optional) is a type of string
  rule_type = null
  # vdc - (optional) is a type of string
  vdc = null

  destination = [{
    exclude            = null
    gateway_interfaces = []
    ip_addresses       = []
    ip_sets            = []
    org_networks       = []
    vm_ids             = []
  }]

  service = [{
    port        = null
    protocol    = null
    source_port = null
  }]

}
```

[top](#index)

### Variables

```terraform
variable "above_rule_id" {
  description = "(optional) - This firewall rule will be inserted above the referred one"
  type        = string
  default     = null
}

variable "action" {
  description = "(optional) - 'accept' or 'deny'. Default 'accept'"
  type        = string
  default     = null
}

variable "edge_gateway" {
  description = "(required) - Edge gateway name in which Firewall Rule is located"
  type        = string
}

variable "enabled" {
  description = "(optional) - Whether the rule should be enabled. Default 'true'"
  type        = bool
  default     = null
}

variable "logging_enabled" {
  description = "(optional) - Whether logging should be enabled for this rule. Default 'false'"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Firewall rule name"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "rule_tag" {
  description = "(optional) - Optional. Allows to set custom rule tag"
  type        = number
  default     = null
}

variable "rule_type" {
  description = "(optional) - Read only. Possible values 'user', 'internal_high'"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "destination" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      exclude            = bool
      gateway_interfaces = set(string)
      ip_addresses       = set(string)
      ip_sets            = set(string)
      org_networks       = set(string)
      vm_ids             = set(string)
    }
  ))
}

variable "service" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      port        = string
      protocol    = string
      source_port = string
    }
  ))
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      exclude            = bool
      gateway_interfaces = set(string)
      ip_addresses       = set(string)
      ip_sets            = set(string)
      org_networks       = set(string)
      vm_ids             = set(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_nsxv_firewall_rule" "this" {
  # above_rule_id - (optional) is a type of string
  above_rule_id = var.above_rule_id
  # action - (optional) is a type of string
  action = var.action
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # logging_enabled - (optional) is a type of bool
  logging_enabled = var.logging_enabled
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # rule_tag - (optional) is a type of number
  rule_tag = var.rule_tag
  # rule_type - (optional) is a type of string
  rule_type = var.rule_type
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "destination" {
    for_each = var.destination
    content {
      # exclude - (optional) is a type of bool
      exclude = destination.value["exclude"]
      # gateway_interfaces - (optional) is a type of set of string
      gateway_interfaces = destination.value["gateway_interfaces"]
      # ip_addresses - (optional) is a type of set of string
      ip_addresses = destination.value["ip_addresses"]
      # ip_sets - (optional) is a type of set of string
      ip_sets = destination.value["ip_sets"]
      # org_networks - (optional) is a type of set of string
      org_networks = destination.value["org_networks"]
      # vm_ids - (optional) is a type of set of string
      vm_ids = destination.value["vm_ids"]
    }
  }

  dynamic "service" {
    for_each = var.service
    content {
      # port - (optional) is a type of string
      port = service.value["port"]
      # protocol - (required) is a type of string
      protocol = service.value["protocol"]
      # source_port - (optional) is a type of string
      source_port = service.value["source_port"]
    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      # exclude - (optional) is a type of bool
      exclude = source.value["exclude"]
      # gateway_interfaces - (optional) is a type of set of string
      gateway_interfaces = source.value["gateway_interfaces"]
      # ip_addresses - (optional) is a type of set of string
      ip_addresses = source.value["ip_addresses"]
      # ip_sets - (optional) is a type of set of string
      ip_sets = source.value["ip_sets"]
      # org_networks - (optional) is a type of set of string
      org_networks = source.value["org_networks"]
      # vm_ids - (optional) is a type of set of string
      vm_ids = source.value["vm_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_nsxv_firewall_rule.this.id
}

output "rule_tag" {
  description = "returns a number"
  value       = vcd_nsxv_firewall_rule.this.rule_tag
}

output "rule_type" {
  description = "returns a string"
  value       = vcd_nsxv_firewall_rule.this.rule_type
}

output "this" {
  value = vcd_nsxv_firewall_rule.this
}
```

[top](#index)