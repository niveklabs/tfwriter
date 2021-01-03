# azurerm_security_center_subscription_pricing

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_security_center_subscription_pricing" {
  source = "./modules/azurerm/r/azurerm_security_center_subscription_pricing"

  # resource_type - (optional) is a type of string
  resource_type = null
  # tier - (required) is a type of string
  tier = null

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
variable "resource_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tier" {
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
resource "azurerm_security_center_subscription_pricing" "this" {
  resource_type = var.resource_type
  tier          = var.tier

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
  value       = azurerm_security_center_subscription_pricing.this.id
}

output "this" {
  value = azurerm_security_center_subscription_pricing.this
}
```

[top](#index)