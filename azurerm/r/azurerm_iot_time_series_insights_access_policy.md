# azurerm_iot_time_series_insights_access_policy

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
module "azurerm_iot_time_series_insights_access_policy" {
  source = "./modules/azurerm/r/azurerm_iot_time_series_insights_access_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # principal_object_id - (required) is a type of string
  principal_object_id = null
  # roles - (required) is a type of set of string
  roles = []
  # time_series_insights_environment_id - (required) is a type of string
  time_series_insights_environment_id = null

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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "principal_object_id" {
  description = "(required)"
  type        = string
}

variable "roles" {
  description = "(required)"
  type        = set(string)
}

variable "time_series_insights_environment_id" {
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
resource "azurerm_iot_time_series_insights_access_policy" "this" {
  description                         = var.description
  name                                = var.name
  principal_object_id                 = var.principal_object_id
  roles                               = var.roles
  time_series_insights_environment_id = var.time_series_insights_environment_id

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
  value       = azurerm_iot_time_series_insights_access_policy.this.id
}

output "this" {
  value = azurerm_iot_time_series_insights_access_policy.this
}
```

[top](#index)