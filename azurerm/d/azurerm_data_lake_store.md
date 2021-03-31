# azurerm_data_lake_store

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
module "azurerm_data_lake_store" {
  source = "./modules/azurerm/d/azurerm_data_lake_store"

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
data "azurerm_data_lake_store" "this" {
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
output "encryption_state" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.encryption_state
}

output "encryption_type" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.encryption_type
}

output "firewall_allow_azure_ips" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.firewall_allow_azure_ips
}

output "firewall_state" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.firewall_state
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_data_lake_store.this.tags
}

output "tier" {
  description = "returns a string"
  value       = data.azurerm_data_lake_store.this.tier
}

output "this" {
  value = azurerm_data_lake_store.this
}
```

[top](#index)