# azurerm_subscription

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
module "azurerm_subscription" {
  source = "./modules/azurerm/d/azurerm_subscription"

  # subscription_id - (optional) is a type of string
  subscription_id = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "subscription_id" {
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
data "azurerm_subscription" "this" {
  # subscription_id - (optional) is a type of string
  subscription_id = var.subscription_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.id
}

output "location_placement_id" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.location_placement_id
}

output "quota_id" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.quota_id
}

output "spending_limit" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.spending_limit
}

output "state" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.state
}

output "subscription_id" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.subscription_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_subscription.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = data.azurerm_subscription.this.tenant_id
}

output "this" {
  value = azurerm_subscription.this
}
```

[top](#index)