# azurerm_virtual_desktop_workspace_application_group_association

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
module "azurerm_virtual_desktop_workspace_application_group_association" {
  source = "./modules/azurerm/r/azurerm_virtual_desktop_workspace_application_group_association"

  # application_group_id - (required) is a type of string
  application_group_id = null
  # workspace_id - (required) is a type of string
  workspace_id = null

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
variable "application_group_id" {
  description = "(required)"
  type        = string
}

variable "workspace_id" {
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
resource "azurerm_virtual_desktop_workspace_application_group_association" "this" {
  application_group_id = var.application_group_id
  workspace_id         = var.workspace_id

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
  value       = azurerm_virtual_desktop_workspace_application_group_association.this.id
}

output "this" {
  value = azurerm_virtual_desktop_workspace_application_group_association.this
}
```

[top](#index)