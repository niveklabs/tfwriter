# azurerm_iothub_shared_access_policy

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
module "azurerm_iothub_shared_access_policy" {
  source = "./modules/azurerm/r/azurerm_iothub_shared_access_policy"

  # device_connect - (optional) is a type of bool
  device_connect = null
  # iothub_name - (required) is a type of string
  iothub_name = null
  # name - (required) is a type of string
  name = null
  # registry_read - (optional) is a type of bool
  registry_read = null
  # registry_write - (optional) is a type of bool
  registry_write = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_connect - (optional) is a type of bool
  service_connect = null

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
variable "device_connect" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "iothub_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "registry_read" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "registry_write" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_connect" {
  description = "(optional)"
  type        = bool
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
resource "azurerm_iothub_shared_access_policy" "this" {
  device_connect      = var.device_connect
  iothub_name         = var.iothub_name
  name                = var.name
  registry_read       = var.registry_read
  registry_write      = var.registry_write
  resource_group_name = var.resource_group_name
  service_connect     = var.service_connect

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
  value       = azurerm_iothub_shared_access_policy.this.id
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurerm_iothub_shared_access_policy.this.primary_connection_string
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = azurerm_iothub_shared_access_policy.this.primary_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_iothub_shared_access_policy.this.secondary_connection_string
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = azurerm_iothub_shared_access_policy.this.secondary_key
  sensitive   = true
}

output "this" {
  value = azurerm_iothub_shared_access_policy.this
}
```

[top](#index)