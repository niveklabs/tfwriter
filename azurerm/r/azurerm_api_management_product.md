# azurerm_api_management_product

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
module "azurerm_api_management_product" {
  source = "./modules/azurerm/r/azurerm_api_management_product"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # approval_required - (optional) is a type of bool
  approval_required = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # product_id - (required) is a type of string
  product_id = null
  # published - (required) is a type of bool
  published = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # subscription_required - (required) is a type of bool
  subscription_required = null
  # subscriptions_limit - (optional) is a type of number
  subscriptions_limit = null
  # terms - (optional) is a type of string
  terms = null

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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "approval_required" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "product_id" {
  description = "(required)"
  type        = string
}

variable "published" {
  description = "(required)"
  type        = bool
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "subscription_required" {
  description = "(required)"
  type        = bool
}

variable "subscriptions_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "terms" {
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
resource "azurerm_api_management_product" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # approval_required - (optional) is a type of bool
  approval_required = var.approval_required
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # product_id - (required) is a type of string
  product_id = var.product_id
  # published - (required) is a type of bool
  published = var.published
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # subscription_required - (required) is a type of bool
  subscription_required = var.subscription_required
  # subscriptions_limit - (optional) is a type of number
  subscriptions_limit = var.subscriptions_limit
  # terms - (optional) is a type of string
  terms = var.terms

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
  value       = azurerm_api_management_product.this.id
}

output "this" {
  value = azurerm_api_management_product.this
}
```

[top](#index)