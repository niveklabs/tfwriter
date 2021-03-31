# nsxt_policy_nat_rule

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_nat_rule" {
  source = "./modules/nsxt/r/nsxt_policy_nat_rule"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # destination_networks - (optional) is a type of list of string
  destination_networks = []
  # display_name - (required) is a type of string
  display_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # firewall_match - (optional) is a type of string
  firewall_match = null
  # gateway_path - (required) is a type of string
  gateway_path = null
  # logging - (optional) is a type of bool
  logging = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # rule_priority - (optional) is a type of number
  rule_priority = null
  # scope - (optional) is a type of list of string
  scope = []
  # service - (optional) is a type of string
  service = null
  # source_networks - (optional) is a type of list of string
  source_networks = []
  # translated_networks - (required) is a type of list of string
  translated_networks = []
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
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "destination_networks" {
  description = "(optional) - The destination network(s) for the NAT Rule"
  type        = list(string)
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "enabled" {
  description = "(optional) - Enable/disable the rule"
  type        = bool
  default     = null
}

variable "firewall_match" {
  description = "(optional) - Firewall match flag"
  type        = string
  default     = null
}

variable "gateway_path" {
  description = "(required) - The NSX-T Policy path to the Tier0 or Tier1 Gateway for this resource"
  type        = string
}

variable "logging" {
  description = "(optional) - Enable/disable the logging of rule"
  type        = bool
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "rule_priority" {
  description = "(optional) - The sequence_number decides the rule_priority of a NAT rule. Valid range [0-2147483647]"
  type        = number
  default     = null
}

variable "scope" {
  description = "(optional) - Policy paths to interfaces or labels where the NAT Rule is enforced"
  type        = list(string)
  default     = null
}

variable "service" {
  description = "(optional) - Policy path of Service on which the NAT rule will be applied"
  type        = string
  default     = null
}

variable "source_networks" {
  description = "(optional) - The source network(s) for the NAT Rule"
  type        = list(string)
  default     = null
}

variable "translated_networks" {
  description = "(required) - The translated network(s) for the NAT Rule"
  type        = list(string)
}

variable "translated_ports" {
  description = "(optional) - Port number or port range. DNAT only"
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
resource "nsxt_policy_nat_rule" "this" {
  action               = var.action
  description          = var.description
  destination_networks = var.destination_networks
  display_name         = var.display_name
  enabled              = var.enabled
  firewall_match       = var.firewall_match
  gateway_path         = var.gateway_path
  logging              = var.logging
  nsx_id               = var.nsx_id
  rule_priority        = var.rule_priority
  scope                = var.scope
  service              = var.service
  source_networks      = var.source_networks
  translated_networks  = var.translated_networks
  translated_ports     = var.translated_ports

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
output "id" {
  description = "returns a string"
  value       = nsxt_policy_nat_rule.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_nat_rule.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_nat_rule.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_nat_rule.this.revision
}

output "scope" {
  description = "returns a list of string"
  value       = nsxt_policy_nat_rule.this.scope
}

output "this" {
  value = nsxt_policy_nat_rule.this
}
```

[top](#index)