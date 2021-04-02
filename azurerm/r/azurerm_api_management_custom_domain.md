# azurerm_api_management_custom_domain

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
module "azurerm_api_management_custom_domain" {
  source = "./modules/azurerm/r/azurerm_api_management_custom_domain"

  # api_management_id - (required) is a type of string
  api_management_id = null

  developer_portal = [{
    certificate                  = null
    certificate_password         = null
    host_name                    = null
    key_vault_id                 = null
    negotiate_client_certificate = null
  }]

  management = [{
    certificate                  = null
    certificate_password         = null
    host_name                    = null
    key_vault_id                 = null
    negotiate_client_certificate = null
  }]

  portal = [{
    certificate                  = null
    certificate_password         = null
    host_name                    = null
    key_vault_id                 = null
    negotiate_client_certificate = null
  }]

  proxy = [{
    certificate                  = null
    certificate_password         = null
    default_ssl_binding          = null
    host_name                    = null
    key_vault_id                 = null
    negotiate_client_certificate = null
  }]

  scm = [{
    certificate                  = null
    certificate_password         = null
    host_name                    = null
    key_vault_id                 = null
    negotiate_client_certificate = null
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
variable "api_management_id" {
  description = "(required)"
  type        = string
}

variable "developer_portal" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate                  = string
      certificate_password         = string
      host_name                    = string
      key_vault_id                 = string
      negotiate_client_certificate = bool
    }
  ))
  default = []
}

variable "management" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate                  = string
      certificate_password         = string
      host_name                    = string
      key_vault_id                 = string
      negotiate_client_certificate = bool
    }
  ))
  default = []
}

variable "portal" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate                  = string
      certificate_password         = string
      host_name                    = string
      key_vault_id                 = string
      negotiate_client_certificate = bool
    }
  ))
  default = []
}

variable "proxy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate                  = string
      certificate_password         = string
      default_ssl_binding          = bool
      host_name                    = string
      key_vault_id                 = string
      negotiate_client_certificate = bool
    }
  ))
  default = []
}

variable "scm" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      certificate                  = string
      certificate_password         = string
      host_name                    = string
      key_vault_id                 = string
      negotiate_client_certificate = bool
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
resource "azurerm_api_management_custom_domain" "this" {
  api_management_id = var.api_management_id

  dynamic "developer_portal" {
    for_each = var.developer_portal
    content {
      certificate                  = developer_portal.value["certificate"]
      certificate_password         = developer_portal.value["certificate_password"]
      host_name                    = developer_portal.value["host_name"]
      key_vault_id                 = developer_portal.value["key_vault_id"]
      negotiate_client_certificate = developer_portal.value["negotiate_client_certificate"]
    }
  }

  dynamic "management" {
    for_each = var.management
    content {
      certificate                  = management.value["certificate"]
      certificate_password         = management.value["certificate_password"]
      host_name                    = management.value["host_name"]
      key_vault_id                 = management.value["key_vault_id"]
      negotiate_client_certificate = management.value["negotiate_client_certificate"]
    }
  }

  dynamic "portal" {
    for_each = var.portal
    content {
      certificate                  = portal.value["certificate"]
      certificate_password         = portal.value["certificate_password"]
      host_name                    = portal.value["host_name"]
      key_vault_id                 = portal.value["key_vault_id"]
      negotiate_client_certificate = portal.value["negotiate_client_certificate"]
    }
  }

  dynamic "proxy" {
    for_each = var.proxy
    content {
      certificate                  = proxy.value["certificate"]
      certificate_password         = proxy.value["certificate_password"]
      default_ssl_binding          = proxy.value["default_ssl_binding"]
      host_name                    = proxy.value["host_name"]
      key_vault_id                 = proxy.value["key_vault_id"]
      negotiate_client_certificate = proxy.value["negotiate_client_certificate"]
    }
  }

  dynamic "scm" {
    for_each = var.scm
    content {
      certificate                  = scm.value["certificate"]
      certificate_password         = scm.value["certificate_password"]
      host_name                    = scm.value["host_name"]
      key_vault_id                 = scm.value["key_vault_id"]
      negotiate_client_certificate = scm.value["negotiate_client_certificate"]
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
  value       = azurerm_api_management_custom_domain.this.id
}

output "this" {
  value = azurerm_api_management_custom_domain.this
}
```

[top](#index)