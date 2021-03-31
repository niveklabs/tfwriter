# azurerm_kusto_attached_database_configuration

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
module "azurerm_kusto_attached_database_configuration" {
  source = "./modules/azurerm/r/azurerm_kusto_attached_database_configuration"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # cluster_resource_id - (required) is a type of string
  cluster_resource_id = null
  # database_name - (required) is a type of string
  database_name = null
  # default_principal_modification_kind - (optional) is a type of string
  default_principal_modification_kind = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "cluster_resource_id" {
  description = "(required)"
  type        = string
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "default_principal_modification_kind" {
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
resource "azurerm_kusto_attached_database_configuration" "this" {
  cluster_name                        = var.cluster_name
  cluster_resource_id                 = var.cluster_resource_id
  database_name                       = var.database_name
  default_principal_modification_kind = var.default_principal_modification_kind
  location                            = var.location
  name                                = var.name
  resource_group_name                 = var.resource_group_name

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
output "attached_database_names" {
  description = "returns a list of string"
  value       = azurerm_kusto_attached_database_configuration.this.attached_database_names
}

output "id" {
  description = "returns a string"
  value       = azurerm_kusto_attached_database_configuration.this.id
}

output "this" {
  value = azurerm_kusto_attached_database_configuration.this
}
```

[top](#index)