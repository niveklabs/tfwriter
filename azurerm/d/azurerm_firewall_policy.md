# azurerm_firewall_policy

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_firewall_policy" {
  source = "./modules/azurerm/d/azurerm_firewall_policy"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_firewall_policy" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "base_policy_id" {
  description = "returns a string"
  value       = data.azurerm_firewall_policy.this.base_policy_id
}

output "child_policies" {
  description = "returns a list of string"
  value       = data.azurerm_firewall_policy.this.child_policies
}

output "dns" {
  description = "returns a list of object"
  value       = data.azurerm_firewall_policy.this.dns
}

output "firewalls" {
  description = "returns a list of string"
  value       = data.azurerm_firewall_policy.this.firewalls
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_firewall_policy.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_firewall_policy.this.location
}

output "rule_collection_groups" {
  description = "returns a list of string"
  value       = data.azurerm_firewall_policy.this.rule_collection_groups
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_firewall_policy.this.tags
}

output "threat_intelligence_allowlist" {
  description = "returns a list of object"
  value       = data.azurerm_firewall_policy.this.threat_intelligence_allowlist
}

output "threat_intelligence_mode" {
  description = "returns a string"
  value       = data.azurerm_firewall_policy.this.threat_intelligence_mode
}

output "this" {
  value = azurerm_firewall_policy.this
}
```

[top](#index)