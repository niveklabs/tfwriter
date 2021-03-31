# azurerm_data_factory_pipeline

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
module "azurerm_data_factory_pipeline" {
  source = "./modules/azurerm/r/azurerm_data_factory_pipeline"

  # activities_json - (optional) is a type of string
  activities_json = null
  # annotations - (optional) is a type of list of string
  annotations = []
  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # variables - (optional) is a type of map of string
  variables = {}

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
variable "activities_json" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "annotations" {
  description = "(optional)"
  type        = list(string)
  default     = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "variables" {
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
resource "azurerm_data_factory_pipeline" "this" {
  activities_json     = var.activities_json
  annotations         = var.annotations
  data_factory_name   = var.data_factory_name
  description         = var.description
  name                = var.name
  parameters          = var.parameters
  resource_group_name = var.resource_group_name
  variables           = var.variables

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
  value       = azurerm_data_factory_pipeline.this.id
}

output "this" {
  value = azurerm_data_factory_pipeline.this
}
```

[top](#index)