# azurerm_app_service

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
module "azurerm_app_service" {
  source = "./modules/azurerm/d/azurerm_app_service"

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
data "azurerm_app_service" "this" {
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
output "app_service_plan_id" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.app_service_plan_id
}

output "app_settings" {
  description = "returns a map of string"
  value       = data.azurerm_app_service.this.app_settings
}

output "client_affinity_enabled" {
  description = "returns a bool"
  value       = data.azurerm_app_service.this.client_affinity_enabled
}

output "client_cert_enabled" {
  description = "returns a bool"
  value       = data.azurerm_app_service.this.client_cert_enabled
}

output "connection_string" {
  description = "returns a list of object"
  value       = data.azurerm_app_service.this.connection_string
}

output "custom_domain_verification_id" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.custom_domain_verification_id
}

output "default_site_hostname" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.default_site_hostname
}

output "enabled" {
  description = "returns a bool"
  value       = data.azurerm_app_service.this.enabled
}

output "https_only" {
  description = "returns a bool"
  value       = data.azurerm_app_service.this.https_only
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.location
}

output "outbound_ip_address_list" {
  description = "returns a list of string"
  value       = data.azurerm_app_service.this.outbound_ip_address_list
}

output "outbound_ip_addresses" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.outbound_ip_addresses
}

output "possible_outbound_ip_address_list" {
  description = "returns a list of string"
  value       = data.azurerm_app_service.this.possible_outbound_ip_address_list
}

output "possible_outbound_ip_addresses" {
  description = "returns a string"
  value       = data.azurerm_app_service.this.possible_outbound_ip_addresses
}

output "site_config" {
  description = "returns a list of object"
  value       = data.azurerm_app_service.this.site_config
}

output "site_credential" {
  description = "returns a list of object"
  value       = data.azurerm_app_service.this.site_credential
}

output "source_control" {
  description = "returns a list of object"
  value       = data.azurerm_app_service.this.source_control
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_app_service.this.tags
}

output "this" {
  value = azurerm_app_service.this
}
```

[top](#index)