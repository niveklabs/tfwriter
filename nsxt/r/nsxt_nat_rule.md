# nsxt_nat_rule

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_nat_rule" {
  source = "./modules/nsxt/r/nsxt_nat_rule"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # logging - (optional) is a type of bool
  logging = null
  # logical_router_id - (required) is a type of string
  logical_router_id = null
  # match_destination_network - (optional) is a type of string
  match_destination_network = null
  # match_source_network - (optional) is a type of string
  match_source_network = null
  # nat_pass - (optional) is a type of bool
  nat_pass = null
  # rule_priority - (optional) is a type of number
  rule_priority = null
  # translated_network - (optional) is a type of string
  translated_network = null
  # translated_ports - (optional) is a type of string
  translated_ports = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required) - The action for the NAT Rule"
  type        = string
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - enable/disable the rule"
  type        = bool
  default     = null
}

variable "logging" {
  description = "(optional) - enable/disable the logging of rule"
  type        = bool
  default     = null
}

variable "logical_router_id" {
  description = "(required) - Logical router id"
  type        = string
}

variable "match_destination_network" {
  description = "(optional) - IP Address | CIDR"
  type        = string
  default     = null
}

variable "match_source_network" {
  description = "(optional) - IP Address | CIDR"
  type        = string
  default     = null
}

variable "nat_pass" {
  description = "(optional) - A boolean flag which reflects whether the following firewall stage will be skipped"
  type        = bool
  default     = null
}

variable "rule_priority" {
  description = "(optional) - The priority of the rule (ascending). Valid range [0-2147483647]"
  type        = number
  default     = null
}

variable "translated_network" {
  description = "(optional) - IP Address | IP Range | CIDR"
  type        = string
  default     = null
}

variable "translated_ports" {
  description = "(optional) - port number or port range. DNAT only"
  type        = string
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_nat_rule" "this" {
  action                    = var.action
  description               = var.description
  display_name              = var.display_name
  enabled                   = var.enabled
  logging                   = var.logging
  logical_router_id         = var.logical_router_id
  match_destination_network = var.match_destination_network
  match_source_network      = var.match_source_network
  nat_pass                  = var.nat_pass
  rule_priority             = var.rule_priority
  translated_network        = var.translated_network
  translated_ports          = var.translated_ports

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_nat_rule.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_nat_rule.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_nat_rule.this.revision
}

output "rule_priority" {
  description = "returns a number"
  value       = nsxt_nat_rule.this.rule_priority
}

output "this" {
  value = nsxt_nat_rule.this
}
```

[top](#index)