# azurerm_kusto_cluster_principal_assignment

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
module "azurerm_kusto_cluster_principal_assignment" {
  source = "./modules/azurerm/r/azurerm_kusto_cluster_principal_assignment"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # name - (required) is a type of string
  name = null
  # principal_id - (required) is a type of string
  principal_id = null
  # principal_type - (required) is a type of string
  principal_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # role - (required) is a type of string
  role = null
  # tenant_id - (required) is a type of string
  tenant_id = null

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

variable "name" {
  description = "(required)"
  type        = string
}

variable "principal_id" {
  description = "(required)"
  type        = string
}

variable "principal_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "tenant_id" {
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
resource "azurerm_kusto_cluster_principal_assignment" "this" {
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
  # name - (required) is a type of string
  name = var.name
  # principal_id - (required) is a type of string
  principal_id = var.principal_id
  # principal_type - (required) is a type of string
  principal_type = var.principal_type
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # role - (required) is a type of string
  role = var.role
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id

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
  value       = azurerm_kusto_cluster_principal_assignment.this.id
}

output "principal_name" {
  description = "returns a string"
  value       = azurerm_kusto_cluster_principal_assignment.this.principal_name
}

output "tenant_name" {
  description = "returns a string"
  value       = azurerm_kusto_cluster_principal_assignment.this.tenant_name
}

output "this" {
  value = azurerm_kusto_cluster_principal_assignment.this
}
```

[top](#index)