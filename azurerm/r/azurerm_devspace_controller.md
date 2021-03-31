# azurerm_devspace_controller

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
module "azurerm_devspace_controller" {
  source = "./modules/azurerm/r/azurerm_devspace_controller"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_container_host_credentials_base64 - (required) is a type of string
  target_container_host_credentials_base64 = null
  # target_container_host_resource_id - (required) is a type of string
  target_container_host_resource_id = null

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

variable "target_container_host_credentials_base64" {
  description = "(required)"
  type        = string
}

variable "target_container_host_resource_id" {
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
resource "azurerm_devspace_controller" "this" {
  location                                 = var.location
  name                                     = var.name
  resource_group_name                      = var.resource_group_name
  sku_name                                 = var.sku_name
  tags                                     = var.tags
  target_container_host_credentials_base64 = var.target_container_host_credentials_base64
  target_container_host_resource_id        = var.target_container_host_resource_id

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
output "data_plane_fqdn" {
  description = "returns a string"
  value       = azurerm_devspace_controller.this.data_plane_fqdn
}

output "host_suffix" {
  description = "returns a string"
  value       = azurerm_devspace_controller.this.host_suffix
}

output "id" {
  description = "returns a string"
  value       = azurerm_devspace_controller.this.id
}

output "this" {
  value = azurerm_devspace_controller.this
}
```

[top](#index)