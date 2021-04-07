# azurerm_key_vault_certificate_issuer

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
module "azurerm_key_vault_certificate_issuer" {
  source = "./modules/azurerm/d/azurerm_key_vault_certificate_issuer"

  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # name - (required) is a type of string
  name = null

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
data "azurerm_key_vault_certificate_issuer" "this" {
  # key_vault_id - (required) is a type of string
  key_vault_id = var.key_vault_id
  # name - (required) is a type of string
  name = var.name

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
output "account_id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_issuer.this.account_id
}

output "admin" {
  description = "returns a list of object"
  value       = data.azurerm_key_vault_certificate_issuer.this.admin
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_issuer.this.id
}

output "org_id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_issuer.this.org_id
}

output "provider_name" {
  description = "returns a string"
  value       = data.azurerm_key_vault_certificate_issuer.this.provider_name
}

output "this" {
  value = azurerm_key_vault_certificate_issuer.this
}
```

[top](#index)