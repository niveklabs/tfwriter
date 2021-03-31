# azurerm_key_vault_certificate_data

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
module "azurerm_key_vault_certificate_data" {
  source = "./modules/azurerm/d/azurerm_key_vault_certificate_data"

  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null
  # version - (optional) is a type of string
  version = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
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
data "azurerm_key_vault_certificate_data" "this" {
  key_vault_id = var.key_vault_id
  name         = var.name
  version      = var.version

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
output "expires" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_data.this.expires
}

output "hex" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_data.this.hex
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_data.this.id
}

output "key" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_data.this.key
  sensitive   = true
}

output "pem" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_data.this.pem
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_key_vault_certificate_data.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_data.this.version
}

output "this" {
  value = azurerm_key_vault_certificate_data.this
}
```

[top](#index)