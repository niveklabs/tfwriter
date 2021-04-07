# azurerm_iothub_fallback_route

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
module "azurerm_iothub_fallback_route" {
  source = "./modules/azurerm/r/azurerm_iothub_fallback_route"

  # condition - (optional) is a type of string
  condition = null
  # enabled - (required) is a type of bool
  enabled = null
  # endpoint_names - (required) is a type of list of string
  endpoint_names = []
  # iothub_name - (required) is a type of string
  iothub_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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
variable "condition" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "endpoint_names" {
  description = "(required)"
  type        = list(string)
}

variable "iothub_name" {
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
resource "azurerm_iothub_fallback_route" "this" {
  # condition - (optional) is a type of string
  condition = var.condition
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # endpoint_names - (required) is a type of list of string
  endpoint_names = var.endpoint_names
  # iothub_name - (required) is a type of string
  iothub_name = var.iothub_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
  value       = azurerm_iothub_fallback_route.this.id
}

output "this" {
  value = azurerm_iothub_fallback_route.this
}
```

[top](#index)