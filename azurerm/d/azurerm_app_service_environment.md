# azurerm_app_service_environment

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
module "azurerm_app_service_environment" {
  source = "./modules/azurerm/d/azurerm_app_service_environment"

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
data "azurerm_app_service_environment" "this" {
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
output "cluster_setting" {
  description = "returns a list of object"
  value       = data.azurerm_app_service_environment.this.cluster_setting
}

output "front_end_scale_factor" {
  description = "returns a number"
  value       = data.azurerm_app_service_environment.this.front_end_scale_factor
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_app_service_environment.this.id
}

output "internal_ip_address" {
  description = "returns a string"
  value       = data.azurerm_app_service_environment.this.internal_ip_address
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_app_service_environment.this.location
}

output "outbound_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_app_service_environment.this.outbound_ip_addresses
}

output "pricing_tier" {
  description = "returns a string"
  value       = data.azurerm_app_service_environment.this.pricing_tier
}

output "service_ip_address" {
  description = "returns a string"
  value       = data.azurerm_app_service_environment.this.service_ip_address
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_app_service_environment.this.tags
}

output "this" {
  value = azurerm_app_service_environment.this
}
```

[top](#index)