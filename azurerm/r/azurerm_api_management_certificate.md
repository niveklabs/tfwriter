# azurerm_api_management_certificate

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
module "azurerm_api_management_certificate" {
  source = "./modules/azurerm/r/azurerm_api_management_certificate"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # data - (required) is a type of string
  data = null
  # name - (required) is a type of string
  name = null
  # password - (optional) is a type of string
  password = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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

variable "data" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "azurerm_api_management_certificate" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # data - (required) is a type of string
  data = var.data
  # name - (required) is a type of string
  name = var.name
  # password - (optional) is a type of string
  password = var.password
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
output "expiration" {
  description = "returns a string"
  value       = azurerm_api_management_certificate.this.expiration
}

output "id" {
  description = "returns a string"
  value       = azurerm_api_management_certificate.this.id
}

output "subject" {
  description = "returns a string"
  value       = azurerm_api_management_certificate.this.subject
}

output "thumbprint" {
  description = "returns a string"
  value       = azurerm_api_management_certificate.this.thumbprint
}

output "this" {
  value = azurerm_api_management_certificate.this
}
```

[top](#index)