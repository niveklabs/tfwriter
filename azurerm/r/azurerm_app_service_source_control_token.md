# azurerm_app_service_source_control_token

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
module "azurerm_app_service_source_control_token" {
  source = "./modules/azurerm/r/azurerm_app_service_source_control_token"

  # token - (required) is a type of string
  token = null
  # token_secret - (optional) is a type of string
  token_secret = null
  # type - (required) is a type of string
  type = null

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
variable "token" {
  description = "(required)"
  type        = string
}

variable "token_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
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
resource "azurerm_app_service_source_control_token" "this" {
  token        = var.token
  token_secret = var.token_secret
  type         = var.type

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
  value       = azurerm_app_service_source_control_token.this.id
}

output "this" {
  value = azurerm_app_service_source_control_token.this
}
```

[top](#index)