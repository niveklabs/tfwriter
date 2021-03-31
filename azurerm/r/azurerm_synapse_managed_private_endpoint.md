# azurerm_synapse_managed_private_endpoint

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
module "azurerm_synapse_managed_private_endpoint" {
  source = "./modules/azurerm/r/azurerm_synapse_managed_private_endpoint"

  # name - (required) is a type of string
  name = null
  # subresource_name - (required) is a type of string
  subresource_name = null
  # synapse_workspace_id - (required) is a type of string
  synapse_workspace_id = null
  # target_resource_id - (required) is a type of string
  target_resource_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
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

variable "subresource_name" {
  description = "(required)"
  type        = string
}

variable "synapse_workspace_id" {
  description = "(required)"
  type        = string
}

variable "target_resource_id" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_synapse_managed_private_endpoint" "this" {
  name                 = var.name
  subresource_name     = var.subresource_name
  synapse_workspace_id = var.synapse_workspace_id
  target_resource_id   = var.target_resource_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_synapse_managed_private_endpoint.this.id
}

output "this" {
  value = azurerm_synapse_managed_private_endpoint.this
}
```

[top](#index)