# azurerm_data_factory_linked_service_sftp

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
module "azurerm_data_factory_linked_service_sftp" {
  source = "./modules/azurerm/r/azurerm_data_factory_linked_service_sftp"

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
  # host - (required) is a type of string
  host = null
  # integration_runtime_name - (optional) is a type of string
  integration_runtime_name = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # password - (required) is a type of string
  password = null
  # port - (required) is a type of number
  port = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # username - (required) is a type of string
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

variable "host" {
  description = "(required)"
  type        = string
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
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "username" {
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_data_factory_linked_service_sftp" "this" {
  additional_properties    = var.additional_properties
  annotations              = var.annotations
  authentication_type      = var.authentication_type
  data_factory_name        = var.data_factory_name
  description              = var.description
  host                     = var.host
  integration_runtime_name = var.integration_runtime_name
  name                     = var.name
  parameters               = var.parameters
  password                 = var.password
  port                     = var.port
  resource_group_name      = var.resource_group_name
  username                 = var.username

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
  value       = azurerm_data_factory_linked_service_sftp.this.id
}

output "this" {
  value = azurerm_data_factory_linked_service_sftp.this
}
```

[top](#index)