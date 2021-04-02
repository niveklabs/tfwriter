# azurerm_firewall

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_firewall" {
  source = "./modules/azurerm/d/azurerm_firewall"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # zones - (optional) is a type of list of string
  zones = []

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

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
data "azurerm_firewall" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
  zones               = var.zones

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
output "dns_servers" {
  description = "returns a list of string"
  value       = data.azurerm_firewall.this.dns_servers
}

output "firewall_policy_id" {
  description = "returns a string"
  value       = data.azurerm_firewall.this.firewall_policy_id
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_firewall.this.id
}

output "ip_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_firewall.this.ip_configuration
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_firewall.this.location
}

output "management_ip_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_firewall.this.management_ip_configuration
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_firewall.this.sku_name
}

output "sku_tier" {
  description = "returns a string"
  value       = data.azurerm_firewall.this.sku_tier
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_firewall.this.tags
}

output "threat_intel_mode" {
  description = "returns a string"
  value       = data.azurerm_firewall.this.threat_intel_mode
}

output "virtual_hub" {
  description = "returns a list of object"
  value       = data.azurerm_firewall.this.virtual_hub
}

output "zones" {
  description = "returns a list of string"
  value       = data.azurerm_firewall.this.zones
}

output "this" {
  value = azurerm_firewall.this
}
```

[top](#index)