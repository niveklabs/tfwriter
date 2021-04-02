# azurerm_service_fabric_mesh_secret_value

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
module "azurerm_service_fabric_mesh_secret_value" {
  source = "./modules/azurerm/r/azurerm_service_fabric_mesh_secret_value"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # service_fabric_mesh_secret_id - (required) is a type of string
  service_fabric_mesh_secret_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # value - (required) is a type of string
  value = null

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

variable "service_fabric_mesh_secret_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "value" {
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
resource "azurerm_service_fabric_mesh_secret_value" "this" {
  location                      = var.location
  name                          = var.name
  service_fabric_mesh_secret_id = var.service_fabric_mesh_secret_id
  tags                          = var.tags
  value                         = var.value

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
  value       = azurerm_service_fabric_mesh_secret_value.this.id
}

output "this" {
  value = azurerm_service_fabric_mesh_secret_value.this
}
```

[top](#index)