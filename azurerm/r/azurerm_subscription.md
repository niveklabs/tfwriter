# azurerm_subscription

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
module "azurerm_subscription" {
  source = "./modules/azurerm/r/azurerm_subscription"

  # alias - (optional) is a type of string
  alias = null
  # billing_scope_id - (optional) is a type of string
  billing_scope_id = null
  # subscription_id - (optional) is a type of string
  subscription_id = null
  # subscription_name - (required) is a type of string
  subscription_name = null
  # workload - (optional) is a type of string
  workload = null

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
variable "alias" {
  description = "(optional) - The Alias Name of the subscription. If omitted a new UUID will be generated for this property."
  type        = string
  default     = null
}

variable "billing_scope_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_id" {
  description = "(optional) - The GUID of the Subscription."
  type        = string
  default     = null
}

variable "subscription_name" {
  description = "(required) - The Display Name for the Subscription."
  type        = string
}

variable "workload" {
  description = "(optional) - The workload type for the Subscription. Possible values are `Production` (default) and `DevTest`."
  type        = string
  default     = null
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
resource "azurerm_subscription" "this" {
  alias             = var.alias
  billing_scope_id  = var.billing_scope_id
  subscription_id   = var.subscription_id
  subscription_name = var.subscription_name
  workload          = var.workload

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
output "alias" {
  description = "returns a string"
  value       = azurerm_subscription.this.alias
}

output "id" {
  description = "returns a string"
  value       = azurerm_subscription.this.id
}

output "subscription_id" {
  description = "returns a string"
  value       = azurerm_subscription.this.subscription_id
}

output "tags" {
  description = "returns a map of string"
  value       = azurerm_subscription.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = azurerm_subscription.this.tenant_id
}

output "this" {
  value = azurerm_subscription.this
}
```

[top](#index)