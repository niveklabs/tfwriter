# vcd_nsxv_firewall_rule

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/vcd/d/vcd_nsxv_firewall_rule"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # org - (optional) is a type of string
  org = null
  # rule_id - (required) is a type of string
  rule_id = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the firewall rule is located"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(required) - Firewall rule ID for lookup"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxv_firewall_rule" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # org - (optional) is a type of string
  org = var.org
  # rule_id - (required) is a type of string
  rule_id = var.rule_id
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.vcd_nsxv_firewall_rule.this.action
}

output "destination" {
  description = "returns a list of object"
  value       = data.vcd_nsxv_firewall_rule.this.destination
}

output "enabled" {
  description = "returns a bool"
  value       = data.vcd_nsxv_firewall_rule.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxv_firewall_rule.this.id
}

output "logging_enabled" {
  description = "returns a bool"
  value       = data.vcd_nsxv_firewall_rule.this.logging_enabled
}

output "name" {
  description = "returns a string"
  value       = data.vcd_nsxv_firewall_rule.this.name
}

output "rule_tag" {
  description = "returns a number"
  value       = data.vcd_nsxv_firewall_rule.this.rule_tag
}

output "rule_type" {
  description = "returns a string"
  value       = data.vcd_nsxv_firewall_rule.this.rule_type
}

output "service" {
  description = "returns a set of object"
  value       = data.vcd_nsxv_firewall_rule.this.service
}

output "source" {
  description = "returns a list of object"
  value       = data.vcd_nsxv_firewall_rule.this.source
}

output "this" {
  value = vcd_nsxv_firewall_rule.this
}
```

[top](#index)