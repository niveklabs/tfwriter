# azurerm_databricks_workspace

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_databricks_workspace" {
  source = "./modules/azurerm/d/azurerm_databricks_workspace"

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
data "azurerm_databricks_workspace" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_databricks_workspace.this.id
}

output "sku" {
  description = "returns a string"
  value       = data.azurerm_databricks_workspace.this.sku
}

output "workspace_id" {
  description = "returns a string"
  value       = data.azurerm_databricks_workspace.this.workspace_id
}

output "workspace_url" {
  description = "returns a string"
  value       = data.azurerm_databricks_workspace.this.workspace_url
}

output "this" {
  value = azurerm_databricks_workspace.this
}
```

[top](#index)