# azurerm_iothub_dps_shared_access_policy

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_iothub_dps_shared_access_policy" {
  source = "./modules/azurerm/d/azurerm_iothub_dps_shared_access_policy"

  # iothub_dps_name - (required) is a type of string
  iothub_dps_name = null
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
variable "iothub_dps_name" {
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
data "azurerm_iothub_dps_shared_access_policy" "this" {
  iothub_dps_name     = var.iothub_dps_name
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
output "id" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps_shared_access_policy.this.id
}

output "primary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps_shared_access_policy.this.primary_connection_string
  sensitive   = true
}

output "primary_key" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps_shared_access_policy.this.primary_key
  sensitive   = true
}

output "secondary_connection_string" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps_shared_access_policy.this.secondary_connection_string
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = data.azurerm_iothub_dps_shared_access_policy.this.secondary_key
  sensitive   = true
}

output "this" {
  value = azurerm_iothub_dps_shared_access_policy.this
}
```

[top](#index)