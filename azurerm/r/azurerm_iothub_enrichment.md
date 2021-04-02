# azurerm_iothub_enrichment

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
module "azurerm_iothub_enrichment" {
  source = "./modules/azurerm/r/azurerm_iothub_enrichment"

  # endpoint_names - (required) is a type of list of string
  endpoint_names = []
  # iothub_name - (required) is a type of string
  iothub_name = null
  # key - (required) is a type of string
  key = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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
variable "endpoint_names" {
  description = "(required)"
  type        = list(string)
}

variable "iothub_name" {
  description = "(required)"
  type        = string
}

variable "key" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
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
resource "azurerm_iothub_enrichment" "this" {
  endpoint_names      = var.endpoint_names
  iothub_name         = var.iothub_name
  key                 = var.key
  resource_group_name = var.resource_group_name
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
  value       = azurerm_iothub_enrichment.this.id
}

output "this" {
  value = azurerm_iothub_enrichment.this
}
```

[top](#index)