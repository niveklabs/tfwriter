# azurerm_cognitive_account

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
module "azurerm_cognitive_account" {
  source = "./modules/azurerm/r/azurerm_cognitive_account"

  # kind - (required) is a type of string
  kind = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # qna_runtime_endpoint - (optional) is a type of string
  qna_runtime_endpoint = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}

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
variable "kind" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "qna_runtime_endpoint" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
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
resource "azurerm_cognitive_account" "this" {
  kind                 = var.kind
  location             = var.location
  name                 = var.name
  qna_runtime_endpoint = var.qna_runtime_endpoint
  resource_group_name  = var.resource_group_name
  sku_name             = var.sku_name
  tags                 = var.tags

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
output "endpoint" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.id
}

output "primary_access_key" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.primary_access_key
  sensitive   = true
}

output "secondary_access_key" {
  description = "returns a string"
  value       = azurerm_cognitive_account.this.secondary_access_key
  sensitive   = true
}

output "this" {
  value = azurerm_cognitive_account.this
}
```

[top](#index)