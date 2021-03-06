# azurerm_data_factory_linked_service_web

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
module "azurerm_data_factory_linked_service_web" {
  source = "./modules/azurerm/r/azurerm_data_factory_linked_service_web"

  # additional_properties - (optional) is a type of map of string
  additional_properties = {}
  # annotations - (optional) is a type of list of string
  annotations = []
  # authentication_type - (required) is a type of string
  authentication_type = null
  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # integration_runtime_name - (optional) is a type of string
  integration_runtime_name = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # password - (optional) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # url - (required) is a type of string
  url = null
  # username - (optional) is a type of string
  username = null

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
variable "additional_properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "annotations" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "authentication_type" {
  description = "(required)"
  type        = string
}

variable "data_factory_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integration_runtime_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "username" {
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
resource "azurerm_data_factory_linked_service_web" "this" {
  # additional_properties - (optional) is a type of map of string
  additional_properties = var.additional_properties
  # annotations - (optional) is a type of list of string
  annotations = var.annotations
  # authentication_type - (required) is a type of string
  authentication_type = var.authentication_type
  # data_factory_name - (required) is a type of string
  data_factory_name = var.data_factory_name
  # description - (optional) is a type of string
  description = var.description
  # integration_runtime_name - (optional) is a type of string
  integration_runtime_name = var.integration_runtime_name
  # name - (required) is a type of string
  name = var.name
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # password - (optional) is a type of string
  password = var.password
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # url - (required) is a type of string
  url = var.url
  # username - (optional) is a type of string
  username = var.username

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
  value       = azurerm_data_factory_linked_service_web.this.id
}

output "this" {
  value = azurerm_data_factory_linked_service_web.this
}
```

[top](#index)