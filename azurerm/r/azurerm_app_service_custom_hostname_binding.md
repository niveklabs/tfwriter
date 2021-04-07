# azurerm_app_service_custom_hostname_binding

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
module "azurerm_app_service_custom_hostname_binding" {
  source = "./modules/azurerm/r/azurerm_app_service_custom_hostname_binding"

  # app_service_name - (required) is a type of string
  app_service_name = null
  # hostname - (required) is a type of string
  hostname = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # ssl_state - (optional) is a type of string
  ssl_state = null
  # thumbprint - (optional) is a type of string
  thumbprint = null

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
variable "app_service_name" {
  description = "(required)"
  type        = string
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "ssl_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "thumbprint" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "azurerm_app_service_custom_hostname_binding" "this" {
  # app_service_name - (required) is a type of string
  app_service_name = var.app_service_name
  # hostname - (required) is a type of string
  hostname = var.hostname
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # ssl_state - (optional) is a type of string
  ssl_state = var.ssl_state
  # thumbprint - (optional) is a type of string
  thumbprint = var.thumbprint

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azurerm_app_service_custom_hostname_binding.this.id
}

output "ssl_state" {
  description = "returns a string"
  value       = azurerm_app_service_custom_hostname_binding.this.ssl_state
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_app_service_custom_hostname_binding.this.thumbprint
}

output "virtual_ip" {
  description = "returns a string"
  value       = azurerm_app_service_custom_hostname_binding.this.virtual_ip
}

output "this" {
  value = azurerm_app_service_custom_hostname_binding.this
}
```

[top](#index)