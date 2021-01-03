# azurerm_api_management

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_api_management" {
  source = "./modules/azurerm/r/azurerm_api_management"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # notification_sender_email - (optional) is a type of string
  notification_sender_email = null
  # policy - (optional) is a type of list of object
  policy = [{
    xml_content = null
    xml_link    = null
  }]
  # publisher_email - (required) is a type of string
  publisher_email = null
  # publisher_name - (required) is a type of string
  publisher_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku_name - (required) is a type of string
  sku_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_network_type - (optional) is a type of string
  virtual_network_type = null

  additional_location = [{
    gateway_regional_url = null
    location             = null
    private_ip_addresses = []
    public_ip_addresses  = []
    virtual_network_configuration = [{
      subnet_id = null
    }]
  }]

  certificate = [{
    certificate_password = null
    encoded_certificate  = null
    store_name           = null
  }]

  hostname_configuration = [{
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
  }]

  identity = [{
    identity_ids = []
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  protocols = [{
    enable_http2 = null
  }]

  security = [{
    enable_backend_ssl30      = null
    enable_backend_tls10      = null
    enable_backend_tls11      = null
    enable_frontend_ssl30     = null
    enable_frontend_tls10     = null
    enable_frontend_tls11     = null
    enable_triple_des_ciphers = null
  }]

  sign_in = [{
    enabled = null
  }]

  sign_up = [{
    enabled = null
    terms_of_service = [{
      consent_required = null
      enabled          = null
      text             = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  virtual_network_configuration = [{
    subnet_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_sender_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type = list(object(
    {
      xml_content = string
      xml_link    = string
    }
  ))
  default = null
}

variable "publisher_email" {
  description = "(required)"
  type        = string
}

variable "publisher_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "additional_location" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      gateway_regional_url = string
      location             = string
      private_ip_addresses = list(string)
      public_ip_addresses  = list(string)
      virtual_network_configuration = list(object(
        {
          subnet_id = string
        }
      ))
    }
  ))
  default = []
}

variable "certificate" {
  description = "nested block: NestingList, min items: 0, max items: 10"
  type = set(object(
    {
      certificate_password = string
      encoded_certificate  = string
      store_name           = string
    }
  ))
  default = []
}

variable "hostname_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      developer_portal = list(object(
        {
          certificate                  = string
          certificate_password         = string
          host_name                    = string
          key_vault_id                 = string
          negotiate_client_certificate = bool
        }
      ))
      management = list(object(
        {
          certificate                  = string
          certificate_password         = string
          host_name                    = string
          key_vault_id                 = string
          negotiate_client_certificate = bool
        }
      ))
      portal = list(object(
        {
          certificate                  = string
          certificate_password         = string
          host_name                    = string
          key_vault_id                 = string
          negotiate_client_certificate = bool
        }
      ))
      proxy = list(object(
        {
          certificate                  = string
          certificate_password         = string
          default_ssl_binding          = bool
          host_name                    = string
          key_vault_id                 = string
          negotiate_client_certificate = bool
        }
      ))
      scm = list(object(
        {
          certificate                  = string
          certificate_password         = string
          host_name                    = string
          key_vault_id                 = string
          negotiate_client_certificate = bool
        }
      ))
    }
  ))
  default = []
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = set(string)
      principal_id = string
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "protocols" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_http2 = bool
    }
  ))
  default = []
}

variable "security" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_backend_ssl30      = bool
      enable_backend_tls10      = bool
      enable_backend_tls11      = bool
      enable_frontend_ssl30     = bool
      enable_frontend_tls10     = bool
      enable_frontend_tls11     = bool
      enable_triple_des_ciphers = bool
    }
  ))
  default = []
}

variable "sign_in" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "sign_up" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
      terms_of_service = list(object(
        {
          consent_required = bool
          enabled          = bool
          text             = string
        }
      ))
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

variable "virtual_network_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      subnet_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_api_management" "this" {
  location                  = var.location
  name                      = var.name
  notification_sender_email = var.notification_sender_email
  policy                    = var.policy
  publisher_email           = var.publisher_email
  publisher_name            = var.publisher_name
  resource_group_name       = var.resource_group_name
  sku_name                  = var.sku_name
  tags                      = var.tags
  virtual_network_type      = var.virtual_network_type

  dynamic "additional_location" {
    for_each = var.additional_location
    content {
      location = additional_location.value["location"]

      dynamic "virtual_network_configuration" {
        for_each = additional_location.value.virtual_network_configuration
        content {
          subnet_id = virtual_network_configuration.value["subnet_id"]
        }
      }

    }
  }

  dynamic "certificate" {
    for_each = var.certificate
    content {
      certificate_password = certificate.value["certificate_password"]
      encoded_certificate  = certificate.value["encoded_certificate"]
      store_name           = certificate.value["store_name"]
    }
  }

  dynamic "hostname_configuration" {
    for_each = var.hostname_configuration
    content {

      dynamic "developer_portal" {
        for_each = hostname_configuration.value.developer_portal
        content {
          certificate                  = developer_portal.value["certificate"]
          certificate_password         = developer_portal.value["certificate_password"]
          host_name                    = developer_portal.value["host_name"]
          key_vault_id                 = developer_portal.value["key_vault_id"]
          negotiate_client_certificate = developer_portal.value["negotiate_client_certificate"]
        }
      }

      dynamic "management" {
        for_each = hostname_configuration.value.management
        content {
          certificate                  = management.value["certificate"]
          certificate_password         = management.value["certificate_password"]
          host_name                    = management.value["host_name"]
          key_vault_id                 = management.value["key_vault_id"]
          negotiate_client_certificate = management.value["negotiate_client_certificate"]
        }
      }

      dynamic "portal" {
        for_each = hostname_configuration.value.portal
        content {
          certificate                  = portal.value["certificate"]
          certificate_password         = portal.value["certificate_password"]
          host_name                    = portal.value["host_name"]
          key_vault_id                 = portal.value["key_vault_id"]
          negotiate_client_certificate = portal.value["negotiate_client_certificate"]
        }
      }

      dynamic "proxy" {
        for_each = hostname_configuration.value.proxy
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
        for_each = hostname_configuration.value.scm
        content {
          certificate                  = scm.value["certificate"]
          certificate_password         = scm.value["certificate_password"]
          host_name                    = scm.value["host_name"]
          key_vault_id                 = scm.value["key_vault_id"]
          negotiate_client_certificate = scm.value["negotiate_client_certificate"]
        }
      }

    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      identity_ids = identity.value["identity_ids"]
      type         = identity.value["type"]
    }
  }

  dynamic "protocols" {
    for_each = var.protocols
    content {
      enable_http2 = protocols.value["enable_http2"]
    }
  }

  dynamic "security" {
    for_each = var.security
    content {
      enable_backend_ssl30      = security.value["enable_backend_ssl30"]
      enable_backend_tls10      = security.value["enable_backend_tls10"]
      enable_backend_tls11      = security.value["enable_backend_tls11"]
      enable_frontend_ssl30     = security.value["enable_frontend_ssl30"]
      enable_frontend_tls10     = security.value["enable_frontend_tls10"]
      enable_frontend_tls11     = security.value["enable_frontend_tls11"]
      enable_triple_des_ciphers = security.value["enable_triple_des_ciphers"]
    }
  }

  dynamic "sign_in" {
    for_each = var.sign_in
    content {
      enabled = sign_in.value["enabled"]
    }
  }

  dynamic "sign_up" {
    for_each = var.sign_up
    content {
      enabled = sign_up.value["enabled"]

      dynamic "terms_of_service" {
        for_each = sign_up.value.terms_of_service
        content {
          consent_required = terms_of_service.value["consent_required"]
          enabled          = terms_of_service.value["enabled"]
          text             = terms_of_service.value["text"]
        }
      }

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

  dynamic "virtual_network_configuration" {
    for_each = var.virtual_network_configuration
    content {
      subnet_id = virtual_network_configuration.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "developer_portal_url" {
  description = "returns a string"
  value       = azurerm_api_management.this.developer_portal_url
}

output "gateway_regional_url" {
  description = "returns a string"
  value       = azurerm_api_management.this.gateway_regional_url
}

output "gateway_url" {
  description = "returns a string"
  value       = azurerm_api_management.this.gateway_url
}

output "id" {
  description = "returns a string"
  value       = azurerm_api_management.this.id
}

output "management_api_url" {
  description = "returns a string"
  value       = azurerm_api_management.this.management_api_url
}

output "notification_sender_email" {
  description = "returns a string"
  value       = azurerm_api_management.this.notification_sender_email
}

output "policy" {
  description = "returns a list of object"
  value       = azurerm_api_management.this.policy
}

output "portal_url" {
  description = "returns a string"
  value       = azurerm_api_management.this.portal_url
}

output "private_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_api_management.this.private_ip_addresses
}

output "public_ip_addresses" {
  description = "returns a list of string"
  value       = azurerm_api_management.this.public_ip_addresses
}

output "scm_url" {
  description = "returns a string"
  value       = azurerm_api_management.this.scm_url
}

output "this" {
  value = azurerm_api_management.this
}
```

[top](#index)