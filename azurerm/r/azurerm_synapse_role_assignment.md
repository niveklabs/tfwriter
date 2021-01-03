# azurerm_synapse_role_assignment

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_synapse_role_assignment" {
  source = "./modules/azurerm/r/azurerm_synapse_role_assignment"

  # principal_id - (required) is a type of string
  principal_id = null
  # role_name - (required) is a type of string
  role_name = null
  # synapse_workspace_id - (required) is a type of string
  synapse_workspace_id = null

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
variable "principal_id" {
  description = "(required)"
  type        = string
}

variable "role_name" {
  description = "(required)"
  type        = string
}

variable "synapse_workspace_id" {
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
resource "azurerm_synapse_role_assignment" "this" {
  principal_id         = var.principal_id
  role_name            = var.role_name
  synapse_workspace_id = var.synapse_workspace_id

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
  value       = azurerm_synapse_role_assignment.this.id
}

output "this" {
  value = azurerm_synapse_role_assignment.this
}
```

[top](#index)