# azurerm_key_vault

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
module "azurerm_key_vault" {
  source = "./modules/azurerm/d/azurerm_key_vault"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

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

variable "resource_group_name" {
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
data "azurerm_key_vault" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
output "access_policy" {
  description = "returns a list of object"
  value       = data.azurerm_key_vault.this.access_policy
}

output "enabled_for_deployment" {
  description = "returns a bool"
  value       = data.azurerm_key_vault.this.enabled_for_deployment
}

output "enabled_for_disk_encryption" {
  description = "returns a bool"
  value       = data.azurerm_key_vault.this.enabled_for_disk_encryption
}

output "enabled_for_template_deployment" {
  description = "returns a bool"
  value       = data.azurerm_key_vault.this.enabled_for_template_deployment
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_key_vault.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_key_vault.this.location
}

output "network_acls" {
  description = "returns a list of object"
  value       = data.azurerm_key_vault.this.network_acls
}

output "purge_protection_enabled" {
  description = "returns a bool"
  value       = data.azurerm_key_vault.this.purge_protection_enabled
}

output "sku_name" {
  description = "returns a string"
  value       = data.azurerm_key_vault.this.sku_name
}

output "soft_delete_enabled" {
  description = "returns a bool"
  value       = data.azurerm_key_vault.this.soft_delete_enabled
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_key_vault.this.tags
}

output "tenant_id" {
  description = "returns a string"
  value       = data.azurerm_key_vault.this.tenant_id
}

output "vault_uri" {
  description = "returns a string"
  value       = data.azurerm_key_vault.this.vault_uri
}

output "this" {
  value = azurerm_key_vault.this
}
```

[top](#index)