# azurerm_data_lake_store

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
module "azurerm_data_lake_store" {
  source = "./modules/azurerm/r/azurerm_data_lake_store"

  # encryption_state - (optional) is a type of string
  encryption_state = null
  # encryption_type - (optional) is a type of string
  encryption_type = null
  # firewall_allow_azure_ips - (optional) is a type of string
  firewall_allow_azure_ips = null
  # firewall_state - (optional) is a type of string
  firewall_state = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tier - (optional) is a type of string
  tier = null

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
variable "encryption_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_allow_azure_ips" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_state" {
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tier" {
  description = "(optional)"
  type        = string
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
resource "azurerm_data_lake_store" "this" {
  # encryption_state - (optional) is a type of string
  encryption_state = var.encryption_state
  # encryption_type - (optional) is a type of string
  encryption_type = var.encryption_type
  # firewall_allow_azure_ips - (optional) is a type of string
  firewall_allow_azure_ips = var.firewall_allow_azure_ips
  # firewall_state - (optional) is a type of string
  firewall_state = var.firewall_state
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # tier - (optional) is a type of string
  tier = var.tier

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
output "encryption_type" {
  description = "returns a string"
  value       = azurerm_data_lake_store.this.encryption_type
}

output "endpoint" {
  description = "returns a string"
  value       = azurerm_data_lake_store.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_data_lake_store.this.id
}

output "this" {
  value = azurerm_data_lake_store.this
}
```

[top](#index)