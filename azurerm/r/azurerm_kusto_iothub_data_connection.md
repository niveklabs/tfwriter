# azurerm_kusto_iothub_data_connection

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
module "azurerm_kusto_iothub_data_connection" {
  source = "./modules/azurerm/r/azurerm_kusto_iothub_data_connection"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # consumer_group - (required) is a type of string
  consumer_group = null
  # database_name - (required) is a type of string
  database_name = null
  # event_system_properties - (optional) is a type of set of string
  event_system_properties = []
  # iothub_id - (required) is a type of string
  iothub_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # shared_access_policy_name - (required) is a type of string
  shared_access_policy_name = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "consumer_group" {
  description = "(required)"
  type        = string
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "event_system_properties" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "iothub_id" {
  description = "(required)"
  type        = string
}

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

variable "shared_access_policy_name" {
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_kusto_iothub_data_connection" "this" {
  cluster_name              = var.cluster_name
  consumer_group            = var.consumer_group
  database_name             = var.database_name
  event_system_properties   = var.event_system_properties
  iothub_id                 = var.iothub_id
  location                  = var.location
  name                      = var.name
  resource_group_name       = var.resource_group_name
  shared_access_policy_name = var.shared_access_policy_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_kusto_iothub_data_connection.this.id
}

output "this" {
  value = azurerm_kusto_iothub_data_connection.this
}
```

[top](#index)