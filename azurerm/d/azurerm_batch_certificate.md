# azurerm_batch_certificate

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
module "azurerm_batch_certificate" {
  source = "./modules/azurerm/d/azurerm_batch_certificate"

  # account_name - (required) is a type of string
  account_name = null
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
variable "account_name" {
  description = "(required)"
  type        = string
}

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
data "azurerm_batch_certificate" "this" {
  # account_name - (required) is a type of string
  account_name = var.account_name
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
output "format" {
  description = "returns a string"
  value       = data.azurerm_batch_certificate.this.format
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_batch_certificate.this.id
}

output "public_data" {
  description = "returns a string"
  value       = data.azurerm_batch_certificate.this.public_data
}

output "thumbprint" {
  description = "returns a string"
  value       = data.azurerm_batch_certificate.this.thumbprint
}

output "thumbprint_algorithm" {
  description = "returns a string"
  value       = data.azurerm_batch_certificate.this.thumbprint_algorithm
}

output "this" {
  value = azurerm_batch_certificate.this
}
```

[top](#index)