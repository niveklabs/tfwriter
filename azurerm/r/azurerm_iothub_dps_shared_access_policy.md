# azurerm_iothub_dps_shared_access_policy

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_iothub_dps_shared_access_policy" {
  source = "./modules/azurerm/r/azurerm_iothub_dps_shared_access_policy"

  # enrollment_read - (optional) is a type of bool
  enrollment_read = null
  # enrollment_write - (optional) is a type of bool
  enrollment_write = null
  # iothub_dps_name - (required) is a type of string
  iothub_dps_name = null
  # name - (required) is a type of string
  name = null
  # registration_read - (optional) is a type of bool
  registration_read = null
  # registration_write - (optional) is a type of bool
  registration_write = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # service_config - (optional) is a type of bool
  service_config = null

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
variable "enrollment_read" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enrollment_write" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "iothub_dps_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "registration_read" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "registration_write" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "service_config" {
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
resource "azurerm_iothub_dps_shared_access_policy" "this" {
  enrollment_read     = var.enrollment_read
  enrollment_write    = var.enrollment_write
  iothub_dps_name     = var.iothub_dps_name
  name                = var.name
  registration_read   = var.registration_read
  registration_write  = var.registration_write
  resource_group_name = var.resource_group_name
  service_config      = var.service_config

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
  value       = azurerm_iothub_dps_shared_access_policy.this.id
}

output "primary_connection_string" {
  description = "returns a string"
  value       = azurerm_iothub_dps_shared_access_policy.this.primary_connection_string
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = azurerm_iothub_dps_shared_access_policy.this.primary_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = azurerm_iothub_dps_shared_access_policy.this.secondary_connection_string
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = azurerm_iothub_dps_shared_access_policy.this.secondary_key
  sensitive   = true
}

output "this" {
  value = azurerm_iothub_dps_shared_access_policy.this
}
```

[top](#index)