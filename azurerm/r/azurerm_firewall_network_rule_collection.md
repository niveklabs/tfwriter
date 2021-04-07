# azurerm_firewall_network_rule_collection

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
module "azurerm_firewall_network_rule_collection" {
  source = "./modules/azurerm/r/azurerm_firewall_network_rule_collection"

  # action - (required) is a type of string
  action = null
  # azure_firewall_name - (required) is a type of string
  azure_firewall_name = null
  # name - (required) is a type of string
  name = null
  # priority - (required) is a type of number
  priority = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  rule = [{
    description           = null
    destination_addresses = []
    destination_fqdns     = []
    destination_ip_groups = []
    destination_ports     = []
    name                  = null
    protocols             = []
    source_addresses      = []
    source_ip_groups      = []
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
variable "action" {
  description = "(required)"
  type        = string
}

variable "azure_firewall_name" {
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      description           = string
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
resource "azurerm_firewall_network_rule_collection" "this" {
  # action - (required) is a type of string
  action = var.action
  # azure_firewall_name - (required) is a type of string
  azure_firewall_name = var.azure_firewall_name
  # name - (required) is a type of string
  name = var.name
  # priority - (required) is a type of number
  priority = var.priority
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "rule" {
    for_each = var.rule
    content {
      # description - (optional) is a type of string
      description = rule.value["description"]
      # destination_addresses - (optional) is a type of set of string
      destination_addresses = rule.value["destination_addresses"]
      # destination_fqdns - (optional) is a type of set of string
      destination_fqdns = rule.value["destination_fqdns"]
      # destination_ip_groups - (optional) is a type of set of string
      destination_ip_groups = rule.value["destination_ip_groups"]
      # destination_ports - (required) is a type of set of string
      destination_ports = rule.value["destination_ports"]
      # name - (required) is a type of string
      name = rule.value["name"]
      # protocols - (required) is a type of set of string
      protocols = rule.value["protocols"]
      # source_addresses - (optional) is a type of set of string
      source_addresses = rule.value["source_addresses"]
      # source_ip_groups - (optional) is a type of set of string
      source_ip_groups = rule.value["source_ip_groups"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_firewall_network_rule_collection.this.id
}

output "this" {
  value = azurerm_firewall_network_rule_collection.this
}
```

[top](#index)