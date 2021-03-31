# azurerm_firewall_policy_rule_collection_group

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_firewall_policy_rule_collection_group" {
  source = "./modules/azurerm/r/azurerm_firewall_policy_rule_collection_group"

  # firewall_policy_id - (required) is a type of string
  firewall_policy_id = null
  # name - (required) is a type of string
  name = null
  # priority - (required) is a type of number
  priority = null

  application_rule_collection = [{
    action   = null
    name     = null
    priority = null
    rule = [{
      destination_fqdn_tags = []
      destination_fqdns     = []
      name                  = null
      protocols = [{
        port = null
        type = null
      }]
      source_addresses = []
      source_ip_groups = []
    }]
  }]

  nat_rule_collection = [{
    action   = null
    name     = null
    priority = null
    rule = [{
      destination_address = null
      destination_ports   = []
      name                = null
      protocols           = []
      source_addresses    = []
      source_ip_groups    = []
      translated_address  = null
      translated_port     = null
    }]
  }]

  network_rule_collection = [{
    action   = null
    name     = null
    priority = null
    rule = [{
      destination_addresses = []
      destination_fqdns     = []
      destination_ip_groups = []
      destination_ports     = []
      name                  = null
      protocols             = []
      source_addresses      = []
      source_ip_groups      = []
    }]
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
variable "firewall_policy_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "application_rule_collection" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      name     = string
      priority = number
      rule = set(object(
        {
          destination_fqdn_tags = set(string)
          destination_fqdns     = set(string)
          name                  = string
          protocols = set(object(
            {
              port = number
              type = string
            }
          ))
          source_addresses = set(string)
          source_ip_groups = set(string)
        }
      ))
    }
  ))
  default = []
}

variable "nat_rule_collection" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      name     = string
      priority = number
      rule = set(object(
        {
          destination_address = string
          destination_ports   = set(string)
          name                = string
          protocols           = set(string)
          source_addresses    = set(string)
          source_ip_groups    = set(string)
          translated_address  = string
          translated_port     = number
        }
      ))
    }
  ))
  default = []
}

variable "network_rule_collection" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action   = string
      name     = string
      priority = number
      rule = set(object(
        {
          destination_addresses = set(string)
          destination_fqdns     = set(string)
          destination_ip_groups = set(string)
          destination_ports     = set(string)
          name                  = string
          protocols             = set(string)
          source_addresses      = set(string)
          source_ip_groups      = set(string)
        }
      ))
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
resource "azurerm_firewall_policy_rule_collection_group" "this" {
  firewall_policy_id = var.firewall_policy_id
  name               = var.name
  priority           = var.priority

  dynamic "application_rule_collection" {
    for_each = var.application_rule_collection
    content {
      action   = application_rule_collection.value["action"]
      name     = application_rule_collection.value["name"]
      priority = application_rule_collection.value["priority"]

      dynamic "rule" {
        for_each = application_rule_collection.value.rule
        content {
          destination_fqdn_tags = rule.value["destination_fqdn_tags"]
          destination_fqdns     = rule.value["destination_fqdns"]
          name                  = rule.value["name"]
          source_addresses      = rule.value["source_addresses"]
          source_ip_groups      = rule.value["source_ip_groups"]

          dynamic "protocols" {
            for_each = rule.value.protocols
            content {
              port = protocols.value["port"]
              type = protocols.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "nat_rule_collection" {
    for_each = var.nat_rule_collection
    content {
      action   = nat_rule_collection.value["action"]
      name     = nat_rule_collection.value["name"]
      priority = nat_rule_collection.value["priority"]

      dynamic "rule" {
        for_each = nat_rule_collection.value.rule
        content {
          destination_address = rule.value["destination_address"]
          destination_ports   = rule.value["destination_ports"]
          name                = rule.value["name"]
          protocols           = rule.value["protocols"]
          source_addresses    = rule.value["source_addresses"]
          source_ip_groups    = rule.value["source_ip_groups"]
          translated_address  = rule.value["translated_address"]
          translated_port     = rule.value["translated_port"]
        }
      }

    }
  }

  dynamic "network_rule_collection" {
    for_each = var.network_rule_collection
    content {
      action   = network_rule_collection.value["action"]
      name     = network_rule_collection.value["name"]
      priority = network_rule_collection.value["priority"]

      dynamic "rule" {
        for_each = network_rule_collection.value.rule
        content {
          destination_addresses = rule.value["destination_addresses"]
          destination_fqdns     = rule.value["destination_fqdns"]
          destination_ip_groups = rule.value["destination_ip_groups"]
          destination_ports     = rule.value["destination_ports"]
          name                  = rule.value["name"]
          protocols             = rule.value["protocols"]
          source_addresses      = rule.value["source_addresses"]
          source_ip_groups      = rule.value["source_ip_groups"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_firewall_policy_rule_collection_group.this.id
}

output "this" {
  value = azurerm_firewall_policy_rule_collection_group.this
}
```

[top](#index)