# azurerm_purview_account

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
module "azurerm_purview_account" {
  source = "./modules/azurerm/r/azurerm_purview_account"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # public_network_enabled - (optional) is a type of bool
  public_network_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_network_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "azurerm_purview_account" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # public_network_enabled - (optional) is a type of bool
  public_network_enabled = var.public_network_enabled
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku_name - (required) is a type of string
  sku_name = var.sku_name
  # tags - (optional) is a type of map of string
  tags = var.tags

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
output "atlas_kafka_endpoint_primary_connection_string" {
  description = "returns a string"
  value       = azurerm_purview_account.this.atlas_kafka_endpoint_primary_connection_string
  sensitive   = true
}

output "atlas_kafka_endpoint_secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_purview_account.this.atlas_kafka_endpoint_secondary_connection_string
  sensitive   = true
}

output "catalog_endpoint" {
  description = "returns a string"
  value       = azurerm_purview_account.this.catalog_endpoint
}

output "guardian_endpoint" {
  description = "returns a string"
  value       = azurerm_purview_account.this.guardian_endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_purview_account.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = azurerm_purview_account.this.identity
}

output "scan_endpoint" {
  description = "returns a string"
  value       = azurerm_purview_account.this.scan_endpoint
}

output "this" {
  value = azurerm_purview_account.this
}
```

[top](#index)