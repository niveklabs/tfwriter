# azurerm_private_link_service

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
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_private_link_service" {
  source = "./modules/azurerm/d/azurerm_private_link_service"

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
data "azurerm_private_link_service" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alias" {
  description = "returns a string"
  value       = data.azurerm_private_link_service.this.alias
}

output "auto_approval_subscription_ids" {
  description = "returns a list of string"
  value       = data.azurerm_private_link_service.this.auto_approval_subscription_ids
}

output "enable_proxy_protocol" {
  description = "returns a bool"
  value       = data.azurerm_private_link_service.this.enable_proxy_protocol
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_private_link_service.this.id
}

output "load_balancer_frontend_ip_configuration_ids" {
  description = "returns a list of string"
  value       = data.azurerm_private_link_service.this.load_balancer_frontend_ip_configuration_ids
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_private_link_service.this.location
}

output "nat_ip_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_private_link_service.this.nat_ip_configuration
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_private_link_service.this.tags
}

output "visibility_subscription_ids" {
  description = "returns a list of string"
  value       = data.azurerm_private_link_service.this.visibility_subscription_ids
}

output "this" {
  value = azurerm_private_link_service.this
}
```

[top](#index)