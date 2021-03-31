# azurerm_databricks_workspace

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
module "azurerm_databricks_workspace" {
  source = "./modules/azurerm/r/azurerm_databricks_workspace"

  # location - (required) is a type of string
  location = null
  # managed_resource_group_name - (optional) is a type of string
  managed_resource_group_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (required) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}

  custom_parameters = [{
    no_public_ip        = null
    private_subnet_name = null
    public_subnet_name  = null
    virtual_network_id  = null
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "managed_resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
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
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "custom_parameters" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      no_public_ip        = bool
      private_subnet_name = string
      public_subnet_name  = string
      virtual_network_id  = string
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
resource "azurerm_databricks_workspace" "this" {
  location                    = var.location
  managed_resource_group_name = var.managed_resource_group_name
  name                        = var.name
  resource_group_name         = var.resource_group_name
  sku                         = var.sku
  tags                        = var.tags

  dynamic "custom_parameters" {
    for_each = var.custom_parameters
    content {
      no_public_ip        = custom_parameters.value["no_public_ip"]
      private_subnet_name = custom_parameters.value["private_subnet_name"]
      public_subnet_name  = custom_parameters.value["public_subnet_name"]
      virtual_network_id  = custom_parameters.value["virtual_network_id"]
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
  value       = azurerm_databricks_workspace.this.id
}

output "managed_resource_group_id" {
  description = "returns a string"
  value       = azurerm_databricks_workspace.this.managed_resource_group_id
}

output "managed_resource_group_name" {
  description = "returns a string"
  value       = azurerm_databricks_workspace.this.managed_resource_group_name
}

output "workspace_id" {
  description = "returns a string"
  value       = azurerm_databricks_workspace.this.workspace_id
}

output "workspace_url" {
  description = "returns a string"
  value       = azurerm_databricks_workspace.this.workspace_url
}

output "this" {
  value = azurerm_databricks_workspace.this
}
```

[top](#index)