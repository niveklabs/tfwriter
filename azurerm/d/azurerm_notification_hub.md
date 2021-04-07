# azurerm_notification_hub

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
module "azurerm_notification_hub" {
  source = "./modules/azurerm/d/azurerm_notification_hub"

  # name - (required) is a type of string
  name = null
  # namespace_name - (required) is a type of string
  namespace_name = null
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

variable "namespace_name" {
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
data "azurerm_notification_hub" "this" {
  # name - (required) is a type of string
  name = var.name
  # namespace_name - (required) is a type of string
  namespace_name = var.namespace_name
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
output "apns_credential" {
  description = "returns a list of object"
  value       = data.azurerm_notification_hub.this.apns_credential
}

output "gcm_credential" {
  description = "returns a list of object"
  value       = data.azurerm_notification_hub.this.gcm_credential
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_notification_hub.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_notification_hub.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_notification_hub.this.tags
}

output "this" {
  value = azurerm_notification_hub.this
}
```

[top](#index)