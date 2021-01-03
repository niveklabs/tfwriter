# azurerm_key_vault_secret

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
module "azurerm_key_vault_secret" {
  source = "./modules/azurerm/r/azurerm_key_vault_secret"

  # content_type - (optional) is a type of string
  content_type = null
  # expiration_date - (optional) is a type of string
  expiration_date = null
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null
  # not_before_date - (optional) is a type of string
  not_before_date = null
  # tags - (optional) is a type of map of string
  tags = {}
  # value - (required) is a type of string
  value = null

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
variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "not_before_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "value" {
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
resource "azurerm_key_vault_secret" "this" {
  content_type    = var.content_type
  expiration_date = var.expiration_date
  key_vault_id    = var.key_vault_id
  name            = var.name
  not_before_date = var.not_before_date
  tags            = var.tags
  value           = var.value

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
  value       = azurerm_key_vault_secret.this.id
}

output "version" {
  description = "returns a string"
  value       = azurerm_key_vault_secret.this.version
}

output "this" {
  value = azurerm_key_vault_secret.this
}
```

[top](#index)