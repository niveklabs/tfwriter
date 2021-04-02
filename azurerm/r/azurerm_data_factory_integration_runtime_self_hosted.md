# azurerm_data_factory_integration_runtime_self_hosted

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
module "azurerm_data_factory_integration_runtime_self_hosted" {
  source = "./modules/azurerm/r/azurerm_data_factory_integration_runtime_self_hosted"

  # data_factory_name - (required) is a type of string
  data_factory_name = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  rbac_authorization = [{
    resource_id = null
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "rbac_authorization" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      resource_id = string
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
resource "azurerm_data_factory_integration_runtime_self_hosted" "this" {
  data_factory_name   = var.data_factory_name
  description         = var.description
  name                = var.name
  resource_group_name = var.resource_group_name

  dynamic "rbac_authorization" {
    for_each = var.rbac_authorization
    content {
      resource_id = rbac_authorization.value["resource_id"]
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
output "auth_key_1" {
  description = "returns a string"
  value       = azurerm_data_factory_integration_runtime_self_hosted.this.auth_key_1
}

output "auth_key_2" {
  description = "returns a string"
  value       = azurerm_data_factory_integration_runtime_self_hosted.this.auth_key_2
}

output "id" {
  description = "returns a string"
  value       = azurerm_data_factory_integration_runtime_self_hosted.this.id
}

output "this" {
  value = azurerm_data_factory_integration_runtime_self_hosted.this
}
```

[top](#index)