# azurerm_container_registry_webhook

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
module "azurerm_container_registry_webhook" {
  source = "./modules/azurerm/r/azurerm_container_registry_webhook"

  # actions - (required) is a type of set of string
  actions = []
  # custom_headers - (optional) is a type of map of string
  custom_headers = {}
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # registry_name - (required) is a type of string
  registry_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # scope - (optional) is a type of string
  scope = null
  # service_uri - (required) is a type of string
  service_uri = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "actions" {
  description = "(required)"
  type        = set(string)
}

variable "custom_headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "registry_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_uri" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_container_registry_webhook" "this" {
  # actions - (required) is a type of set of string
  actions = var.actions
  # custom_headers - (optional) is a type of map of string
  custom_headers = var.custom_headers
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # registry_name - (required) is a type of string
  registry_name = var.registry_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # scope - (optional) is a type of string
  scope = var.scope
  # service_uri - (required) is a type of string
  service_uri = var.service_uri
  # status - (optional) is a type of string
  status = var.status
  # tags - (optional) is a type of map of string
  tags = var.tags

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
  value       = azurerm_container_registry_webhook.this.id
}

output "this" {
  value = azurerm_container_registry_webhook.this
}
```

[top](#index)