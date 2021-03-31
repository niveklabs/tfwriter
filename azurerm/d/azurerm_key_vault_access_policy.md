# azurerm_key_vault_access_policy

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
module "azurerm_key_vault_access_policy" {
  source = "./modules/azurerm/d/azurerm_key_vault_access_policy"

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
data "azurerm_key_vault_access_policy" "this" {
  name = var.name

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
output "certificate_permissions" {
  description = "returns a list of string"
  value       = data.azurerm_key_vault_access_policy.this.certificate_permissions
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault_access_policy.this.id
}

output "key_permissions" {
  description = "returns a list of string"
  value       = data.azurerm_key_vault_access_policy.this.key_permissions
}

output "secret_permissions" {
  description = "returns a list of string"
  value       = data.azurerm_key_vault_access_policy.this.secret_permissions
}

output "this" {
  value = azurerm_key_vault_access_policy.this
}
```

[top](#index)