# azurerm_api_management_identity_provider_twitter

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
module "azurerm_api_management_identity_provider_twitter" {
  source = "./modules/azurerm/r/azurerm_api_management_identity_provider_twitter"

  # api_key - (required) is a type of string
  api_key = null
  # api_management_name - (required) is a type of string
  api_management_name = null
  # api_secret_key - (required) is a type of string
  api_secret_key = null
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
variable "api_key" {
  description = "(required)"
  type        = string
}

variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "api_secret_key" {
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
resource "azurerm_api_management_identity_provider_twitter" "this" {
  # api_key - (required) is a type of string
  api_key = var.api_key
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # api_secret_key - (required) is a type of string
  api_secret_key = var.api_secret_key
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
output "id" {
  description = "returns a string"
  value       = azurerm_api_management_identity_provider_twitter.this.id
}

output "this" {
  value = azurerm_api_management_identity_provider_twitter.this
}
```

[top](#index)