# azurerm_batch_certificate

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
module "azurerm_batch_certificate" {
  source = "./modules/azurerm/r/azurerm_batch_certificate"

  # account_name - (required) is a type of string
  account_name = null
  # certificate - (required) is a type of string
  certificate = null
  # format - (required) is a type of string
  format = null
  # password - (optional) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # thumbprint - (required) is a type of string
  thumbprint = null
  # thumbprint_algorithm - (required) is a type of string
  thumbprint_algorithm = null

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
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "certificate" {
  description = "(required)"
  type        = string
}

variable "format" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "thumbprint" {
  description = "(required)"
  type        = string
}

variable "thumbprint_algorithm" {
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
resource "azurerm_batch_certificate" "this" {
  account_name         = var.account_name
  certificate          = var.certificate
  format               = var.format
  password             = var.password
  resource_group_name  = var.resource_group_name
  thumbprint           = var.thumbprint
  thumbprint_algorithm = var.thumbprint_algorithm

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
  value       = azurerm_batch_certificate.this.id
}

output "name" {
  description = "returns a string"
  value       = azurerm_batch_certificate.this.name
}

output "public_data" {
  description = "returns a string"
  value       = azurerm_batch_certificate.this.public_data
}

output "this" {
  value = azurerm_batch_certificate.this
}
```

[top](#index)