# azurerm_key_vault

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
module "azurerm_key_vault" {
  source = "./modules/azurerm/r/azurerm_key_vault"

  # access_policy - (optional) is a type of list of object
  access_policy = [{
    application_id          = null
    certificate_permissions = []
    key_permissions         = []
    object_id               = null
    secret_permissions      = []
    storage_permissions     = []
    tenant_id               = null
  }]
  # enable_rbac_authorization - (optional) is a type of bool
  enable_rbac_authorization = null
  # enabled_for_deployment - (optional) is a type of bool
  enabled_for_deployment = null
  # enabled_for_disk_encryption - (optional) is a type of bool
  enabled_for_disk_encryption = null
  # enabled_for_template_deployment - (optional) is a type of bool
  enabled_for_template_deployment = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # purge_protection_enabled - (optional) is a type of bool
  purge_protection_enabled = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # soft_delete_enabled - (optional) is a type of bool
  soft_delete_enabled = null
  # soft_delete_retention_days - (optional) is a type of number
  soft_delete_retention_days = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_id - (required) is a type of string
  tenant_id = null

  contact = [{
    email = null
    name  = null
    phone = null
  }]

  network_acls = [{
    bypass                     = null
    default_action             = null
    ip_rules                   = []
    virtual_network_subnet_ids = []
  }]

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
variable "access_policy" {
  description = "(optional)"
  type = list(object(
    {
      application_id          = string
      certificate_permissions = list(string)
      key_permissions         = list(string)
      object_id               = string
      secret_permissions      = list(string)
      storage_permissions     = list(string)
      tenant_id               = string
    }
  ))
  default = null
}

variable "enable_rbac_authorization" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled_for_deployment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled_for_disk_encryption" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled_for_template_deployment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "purge_protection_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "soft_delete_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "soft_delete_retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tenant_id" {
  description = "(required)"
  type        = string
}

variable "contact" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      email = string
      name  = string
      phone = string
    }
  ))
  default = []
}

variable "network_acls" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bypass                     = string
      default_action             = string
      ip_rules                   = set(string)
      virtual_network_subnet_ids = set(string)
    }
  ))
  default = []
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
resource "azurerm_key_vault" "this" {
  access_policy                   = var.access_policy
  enable_rbac_authorization       = var.enable_rbac_authorization
  enabled_for_deployment          = var.enabled_for_deployment
  enabled_for_disk_encryption     = var.enabled_for_disk_encryption
  enabled_for_template_deployment = var.enabled_for_template_deployment
  location                        = var.location
  name                            = var.name
  purge_protection_enabled        = var.purge_protection_enabled
  resource_group_name             = var.resource_group_name
  sku_name                        = var.sku_name
  soft_delete_enabled             = var.soft_delete_enabled
  soft_delete_retention_days      = var.soft_delete_retention_days
  tags                            = var.tags
  tenant_id                       = var.tenant_id

  dynamic "contact" {
    for_each = var.contact
    content {
      email = contact.value["email"]
      name  = contact.value["name"]
      phone = contact.value["phone"]
    }
  }

  dynamic "network_acls" {
    for_each = var.network_acls
    content {
      bypass                     = network_acls.value["bypass"]
      default_action             = network_acls.value["default_action"]
      ip_rules                   = network_acls.value["ip_rules"]
      virtual_network_subnet_ids = network_acls.value["virtual_network_subnet_ids"]
    }
  }

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
output "access_policy" {
  description = "returns a list of object"
  value       = azurerm_key_vault.this.access_policy
}

output "id" {
  description = "returns a string"
  value       = azurerm_key_vault.this.id
}

output "soft_delete_enabled" {
  description = "returns a bool"
  value       = azurerm_key_vault.this.soft_delete_enabled
}

output "vault_uri" {
  description = "returns a string"
  value       = azurerm_key_vault.this.vault_uri
}

output "this" {
  value = azurerm_key_vault.this
}
```

[top](#index)