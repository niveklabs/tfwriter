# azurerm_data_factory_dataset_mysql

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
module "azurerm_data_factory_dataset_mysql" {
  source = "./modules/azurerm/r/azurerm_data_factory_dataset_mysql"

  # additional_properties - (optional) is a type of map of string
  additional_properties = {}
  # annotations - (optional) is a type of list of string
  annotations = []
  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # folder - (optional) is a type of string
  folder = null
  # linked_service_name - (required) is a type of string
  linked_service_name = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # table_name - (optional) is a type of string
  table_name = null

  schema_column = [{
    description = null
    name        = null
    type        = null
  }]

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

variable "data_factory_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "folder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "linked_service_name" {
  description = "(required)"
  type        = string
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

variable "table_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "schema_column" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      name        = string
      type        = string
    }
  ))
  default = []
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
resource "azurerm_data_factory_dataset_mysql" "this" {
  additional_properties = var.additional_properties
  annotations           = var.annotations
  data_factory_name     = var.data_factory_name
  description           = var.description
  folder                = var.folder
  linked_service_name   = var.linked_service_name
  name                  = var.name
  parameters            = var.parameters
  resource_group_name   = var.resource_group_name
  table_name            = var.table_name

  dynamic "schema_column" {
    for_each = var.schema_column
    content {
      description = schema_column.value["description"]
      name        = schema_column.value["name"]
      type        = schema_column.value["type"]
    }
  }

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
  value       = azurerm_data_factory_dataset_mysql.this.id
}

output "this" {
  value = azurerm_data_factory_dataset_mysql.this
}
```

[top](#index)