# azurerm_frontdoor_custom_https_configuration

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
module "azurerm_frontdoor_custom_https_configuration" {
  source = "./modules/azurerm/r/azurerm_frontdoor_custom_https_configuration"

  # custom_https_provisioning_enabled - (required) is a type of bool
  custom_https_provisioning_enabled = null
  # frontend_endpoint_id - (required) is a type of string
  frontend_endpoint_id = null
  # resource_group_name - (optional) is a type of string
  resource_group_name = null

  custom_https_configuration = [{
    azure_key_vault_certificate_secret_name    = null
    azure_key_vault_certificate_secret_version = null
    azure_key_vault_certificate_vault_id       = null
    certificate_source                         = null
    minimum_tls_version                        = null
    provisioning_state                         = null
    provisioning_substate                      = null
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
variable "custom_https_provisioning_enabled" {
  description = "(required)"
  type        = bool
}

variable "frontend_endpoint_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_https_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      azure_key_vault_certificate_secret_name    = string
      azure_key_vault_certificate_secret_version = string
      azure_key_vault_certificate_vault_id       = string
      certificate_source                         = string
      minimum_tls_version                        = string
      provisioning_state                         = string
      provisioning_substate                      = string
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
resource "azurerm_frontdoor_custom_https_configuration" "this" {
  custom_https_provisioning_enabled = var.custom_https_provisioning_enabled
  frontend_endpoint_id              = var.frontend_endpoint_id
  resource_group_name               = var.resource_group_name

  dynamic "custom_https_configuration" {
    for_each = var.custom_https_configuration
    content {
      azure_key_vault_certificate_secret_name    = custom_https_configuration.value["azure_key_vault_certificate_secret_name"]
      azure_key_vault_certificate_secret_version = custom_https_configuration.value["azure_key_vault_certificate_secret_version"]
      azure_key_vault_certificate_vault_id       = custom_https_configuration.value["azure_key_vault_certificate_vault_id"]
      certificate_source                         = custom_https_configuration.value["certificate_source"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_frontdoor_custom_https_configuration.this.id
}

output "this" {
  value = azurerm_frontdoor_custom_https_configuration.this
}
```

[top](#index)