# azurerm_api_management

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
module "azurerm_api_management" {
  source = "./modules/azurerm/d/azurerm_api_management"

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
data "azurerm_api_management" "this" {
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
output "additional_location" {
  description = "returns a list of object"
  value       = data.azurerm_api_management.this.additional_location
}

output "developer_portal_url" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.developer_portal_url
}

output "gateway_regional_url" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.gateway_regional_url
}

output "gateway_url" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.gateway_url
}

output "hostname_configuration" {
  description = "returns a list of object"
  value       = data.azurerm_api_management.this.hostname_configuration
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = data.azurerm_api_management.this.identity
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.location
}

output "management_api_url" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.management_api_url
}

output "notification_sender_email" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.notification_sender_email
}

output "portal_url" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.portal_url
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_api_management.this.private_ip_addresses
}

output "public_ip_addresses" {
  description = "returns a list of string"
  value       = data.azurerm_api_management.this.public_ip_addresses
}

output "publisher_email" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.publisher_email
}

output "publisher_name" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.publisher_name
}

output "scm_url" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.scm_url
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_api_management.this.sku_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_api_management.this.tags
}

output "this" {
  value = azurerm_api_management.this
}
```

[top](#index)