# azurerm_iothub_route

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
module "azurerm_iothub_route" {
  source = null

  # condition - (optional) is a type of string
  condition = null
  # enabled - (required) is a type of bool
  enabled = null
  # endpoint_names - (required) is a type of list of string
  endpoint_names = []
  # iothub_name - (required) is a type of string
  iothub_name = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source - (required) is a type of string

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

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source" {
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
resource "azurerm_iothub_route" "this" {
  condition           = var.condition
  enabled             = var.enabled
  endpoint_names      = var.endpoint_names
  iothub_name         = var.iothub_name
  name                = var.name
  resource_group_name = var.resource_group_name
  source              = var.source

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
  value       = azurerm_iothub_route.this.id
}

output "this" {
  value = azurerm_iothub_route.this
}
```

[top](#index)