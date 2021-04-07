# azurerm_firewall_policy

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_firewall_policy" {
  source = "./modules/azurerm/r/azurerm_firewall_policy"

  # base_policy_id - (optional) is a type of string
  base_policy_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (optional) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}
  # threat_intelligence_mode - (optional) is a type of string
  threat_intelligence_mode = null

  dns = [{
    network_rule_fqdn_enabled = null
    proxy_enabled             = null
    servers                   = []
  }]

  threat_intelligence_allowlist = [{
    fqdns        = []
    ip_addresses = []
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_policy_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "threat_intelligence_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      network_rule_fqdn_enabled = bool
      proxy_enabled             = bool
      servers                   = set(string)
    }
  ))
  default = []
}

variable "threat_intelligence_allowlist" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      fqdns        = set(string)
      ip_addresses = set(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_firewall_policy" "this" {
  # base_policy_id - (optional) is a type of string
  base_policy_id = var.base_policy_id
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku - (optional) is a type of string
  sku = var.sku
  # tags - (optional) is a type of map of string
  tags = var.tags
  # threat_intelligence_mode - (optional) is a type of string
  threat_intelligence_mode = var.threat_intelligence_mode

  dynamic "dns" {
    for_each = var.dns
    content {
      # network_rule_fqdn_enabled - (optional) is a type of bool
      network_rule_fqdn_enabled = dns.value["network_rule_fqdn_enabled"]
      # proxy_enabled - (optional) is a type of bool
      proxy_enabled = dns.value["proxy_enabled"]
      # servers - (optional) is a type of set of string
      servers = dns.value["servers"]
    }
  }

  dynamic "threat_intelligence_allowlist" {
    for_each = var.threat_intelligence_allowlist
    content {
      # fqdns - (optional) is a type of set of string
      fqdns = threat_intelligence_allowlist.value["fqdns"]
      # ip_addresses - (optional) is a type of set of string
      ip_addresses = threat_intelligence_allowlist.value["ip_addresses"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "child_policies" {
  description = "returns a list of string"
  value       = azurerm_firewall_policy.this.child_policies
}

output "firewalls" {
  description = "returns a list of string"
  value       = azurerm_firewall_policy.this.firewalls
}

output "id" {
  description = "returns a string"
  value       = azurerm_firewall_policy.this.id
}

output "rule_collection_groups" {
  description = "returns a list of string"
  value       = azurerm_firewall_policy.this.rule_collection_groups
}

output "sku" {
  description = "returns a string"
  value       = azurerm_firewall_policy.this.sku
}

output "this" {
  value = azurerm_firewall_policy.this
}
```

[top](#index)