# azurerm_key_vault_certificate

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_key_vault_certificate" {
  source = "./modules/azurerm/d/azurerm_key_vault_certificate"

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
data "azurerm_key_vault_certificate" "this" {
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
output "certificate_data" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate.this.certificate_data
}

output "certificate_policy" {
  description = "returns a list of object"
  value       = data.azurerm_key_vault_certificate.this.certificate_policy
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate.this.id
}

output "secret_id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate.this.secret_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_key_vault_certificate.this.tags
}

output "thumbprint" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate.this.thumbprint
}

output "version" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate.this.version
}

output "this" {
  value = azurerm_key_vault_certificate.this
}
```

[top](#index)