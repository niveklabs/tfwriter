# azurerm_api_management_product

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_api_management_product" {
  source = "./modules/azurerm/d/azurerm_api_management_product"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # product_id - (required) is a type of string
  product_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
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

variable "product_id" {
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
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_api_management_product" "this" {
  api_management_name = var.api_management_name
  product_id          = var.product_id
  resource_group_name = var.resource_group_name

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
output "approval_required" {
  description = "returns a bool"
  value       = data.azurerm_api_management_product.this.approval_required
}

output "description" {
  description = "returns a string"
  value       = data.azurerm_api_management_product.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.azurerm_api_management_product.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_api_management_product.this.id
}

output "published" {
  description = "returns a bool"
  value       = data.azurerm_api_management_product.this.published
}

output "subscription_required" {
  description = "returns a bool"
  value       = data.azurerm_api_management_product.this.subscription_required
}

output "subscriptions_limit" {
  description = "returns a number"
  value       = data.azurerm_api_management_product.this.subscriptions_limit
}

output "terms" {
  description = "returns a string"
  value       = data.azurerm_api_management_product.this.terms
}

output "this" {
  value = azurerm_api_management_product.this
}
```

[top](#index)