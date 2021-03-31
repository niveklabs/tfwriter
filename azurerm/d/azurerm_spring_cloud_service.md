# azurerm_spring_cloud_service

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_spring_cloud_service" {
  source = "./modules/azurerm/d/azurerm_spring_cloud_service"

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
data "azurerm_spring_cloud_service" "this" {
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
output "config_server_git_setting" {
  description = "returns a list of object"
  value       = data.azurerm_spring_cloud_service.this.config_server_git_setting
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_spring_cloud_service.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_spring_cloud_service.this.location
}

output "outbound_public_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_spring_cloud_service.this.outbound_public_ip_addresses
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_spring_cloud_service.this.tags
}

output "this" {
  value = azurerm_spring_cloud_service.this
}
```

[top](#index)