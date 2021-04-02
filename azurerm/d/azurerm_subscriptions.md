# azurerm_subscriptions

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "azurerm_subscriptions" {
  source = "./modules/azurerm/d/azurerm_subscriptions"

  # display_name_contains - (optional) is a type of string
  display_name_contains = null
  # display_name_prefix - (optional) is a type of string
  display_name_prefix = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "display_name_contains" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_subscriptions" "this" {
  display_name_contains = var.display_name_contains
  display_name_prefix   = var.display_name_prefix

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurerm_subscriptions.this.id
}

output "subscriptions" {
  description = "returns a list of object"
  value       = data.azurerm_subscriptions.this.subscriptions
}

output "this" {
  value = azurerm_subscriptions.this
}
```

[top](#index)