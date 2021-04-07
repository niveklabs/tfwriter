# azurerm_api_management_subscription

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
module "azurerm_api_management_subscription" {
  source = "./modules/azurerm/r/azurerm_api_management_subscription"

  # allow_tracing - (optional) is a type of bool
  allow_tracing = null
  # api_management_name - (required) is a type of string
  api_management_name = null
  # display_name - (required) is a type of string
  display_name = null
  # primary_key - (optional) is a type of string
  primary_key = null
  # product_id - (optional) is a type of string
  product_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # secondary_key - (optional) is a type of string
  secondary_key = null
  # state - (optional) is a type of string
  state = null
  # subscription_id - (optional) is a type of string
  subscription_id = null
  # user_id - (optional) is a type of string
  user_id = null

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
variable "allow_tracing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "primary_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "product_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "secondary_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
  description = "(optional)"
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
resource "azurerm_api_management_subscription" "this" {
  # allow_tracing - (optional) is a type of bool
  allow_tracing = var.allow_tracing
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # display_name - (required) is a type of string
  display_name = var.display_name
  # primary_key - (optional) is a type of string
  primary_key = var.primary_key
  # product_id - (optional) is a type of string
  product_id = var.product_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # secondary_key - (optional) is a type of string
  secondary_key = var.secondary_key
  # state - (optional) is a type of string
  state = var.state
  # subscription_id - (optional) is a type of string
  subscription_id = var.subscription_id
  # user_id - (optional) is a type of string
  user_id = var.user_id

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
  value       = azurerm_api_management_subscription.this.id
}

output "primary_key" {
  description = "returns a string"
  value       = azurerm_api_management_subscription.this.primary_key
  sensitive   = true
}

output "secondary_key" {
  description = "returns a string"
  value       = azurerm_api_management_subscription.this.secondary_key
  sensitive   = true
}

output "subscription_id" {
  description = "returns a string"
  value       = azurerm_api_management_subscription.this.subscription_id
}

output "this" {
  value = azurerm_api_management_subscription.this
}
```

[top](#index)