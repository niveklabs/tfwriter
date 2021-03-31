# azurerm_api_management_api_schema

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
module "azurerm_api_management_api_schema" {
  source = "./modules/azurerm/r/azurerm_api_management_api_schema"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # api_name - (required) is a type of string
  api_name = null
  # content_type - (required) is a type of string
  content_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # value - (required) is a type of string
  value = null

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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "api_name" {
  description = "(required)"
  type        = string
}

variable "content_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "value" {
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
resource "azurerm_api_management_api_schema" "this" {
  api_management_name = var.api_management_name
  api_name            = var.api_name
  content_type        = var.content_type
  resource_group_name = var.resource_group_name
  schema_id           = var.schema_id
  value               = var.value

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
  value       = azurerm_api_management_api_schema.this.id
}

output "this" {
  value = azurerm_api_management_api_schema.this
}
```

[top](#index)