# azurerm_key_vault_key

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
module "azurerm_key_vault_key" {
  source = "./modules/azurerm/r/azurerm_key_vault_key"

  # curve - (optional) is a type of string
  curve = null
  # expiration_date - (optional) is a type of string
  expiration_date = null
  # key_opts - (required) is a type of list of string
  key_opts = []
  # key_size - (optional) is a type of number
  key_size = null
  # key_type - (required) is a type of string
  key_type = null
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null
  # not_before_date - (optional) is a type of string
  not_before_date = null
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
variable "curve" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expiration_date" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_opts" {
  description = "(required)"
  type        = list(string)
}

variable "key_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "key_type" {
  description = "(required)"
  type        = string
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
resource "azurerm_key_vault_key" "this" {
  curve           = var.curve
  expiration_date = var.expiration_date
  key_opts        = var.key_opts
  key_size        = var.key_size
  key_type        = var.key_type
  key_vault_id    = var.key_vault_id
  name            = var.name
  not_before_date = var.not_before_date
  tags            = var.tags

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
output "curve" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.curve
}

output "e" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.e
}

output "id" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.id
}

output "n" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.n
}

output "version" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.version
}

output "versionless_id" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.versionless_id
}

output "x" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.x
}

output "y" {
  description = "returns a string"
  value       = azurerm_key_vault_key.this.y
}

output "this" {
  value = azurerm_key_vault_key.this
}
```

[top](#index)