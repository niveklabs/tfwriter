# azurerm_cognitive_account

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
module "azurerm_cognitive_account" {
  source = "./modules/azurerm/d/azurerm_cognitive_account"

  # name - (required) is a type of string
  name = null
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
variable "name" {
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
data "azurerm_cognitive_account" "this" {
  name                = var.name
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
output "endpoint" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.id
}

output "kind" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.kind
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.location
}

output "primary_access_key" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.primary_access_key
  sensitive   = true
}

output "qna_runtime_endpoint" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.qna_runtime_endpoint
}

output "secondary_access_key" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.secondary_access_key
  sensitive   = true
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_cognitive_account.this.sku_name
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_cognitive_account.this.tags
}

output "this" {
  value = azurerm_cognitive_account.this
}
```

[top](#index)