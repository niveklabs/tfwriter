# azurerm_key_vault_access_policy

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
module "azurerm_key_vault_access_policy" {
  source = "./modules/azurerm/r/azurerm_key_vault_access_policy"

  # application_id - (optional) is a type of string
  application_id = null
  # certificate_permissions - (optional) is a type of list of string
  certificate_permissions = []
  # key_permissions - (optional) is a type of list of string
  key_permissions = []
  # key_vault_id - (required) is a type of string
  key_vault_id = null
  # object_id - (required) is a type of string
  object_id = null
  # secret_permissions - (optional) is a type of list of string
  secret_permissions = []
  # storage_permissions - (optional) is a type of list of string
  storage_permissions = []
  # tenant_id - (required) is a type of string
  tenant_id = null

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
variable "application_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "certificate_permissions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "key_permissions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "key_vault_id" {
  description = "(required)"
  type        = string
}

variable "object_id" {
  description = "(required)"
  type        = string
}

variable "secret_permissions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "storage_permissions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tenant_id" {
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
resource "azurerm_key_vault_access_policy" "this" {
  # application_id - (optional) is a type of string
  application_id = var.application_id
  # certificate_permissions - (optional) is a type of list of string
  certificate_permissions = var.certificate_permissions
  # key_permissions - (optional) is a type of list of string
  key_permissions = var.key_permissions
  # key_vault_id - (required) is a type of string
  key_vault_id = var.key_vault_id
  # object_id - (required) is a type of string
  object_id = var.object_id
  # secret_permissions - (optional) is a type of list of string
  secret_permissions = var.secret_permissions
  # storage_permissions - (optional) is a type of list of string
  storage_permissions = var.storage_permissions
  # tenant_id - (required) is a type of string
  tenant_id = var.tenant_id

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
  value       = azurerm_key_vault_access_policy.this.id
}

output "this" {
  value = azurerm_key_vault_access_policy.this
}
```

[top](#index)