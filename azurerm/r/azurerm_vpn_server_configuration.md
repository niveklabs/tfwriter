# azurerm_vpn_server_configuration

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
module "azurerm_vpn_server_configuration" {
  source = "./modules/azurerm/r/azurerm_vpn_server_configuration"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpn_authentication_types - (required) is a type of list of string
  vpn_authentication_types = []
  # vpn_protocols - (optional) is a type of set of string
  vpn_protocols = []

  azure_active_directory_authentication = [{
    audience = null
    issuer   = null
    tenant   = null
  }]

  client_revoked_certificate = [{
    name       = null
    thumbprint = null
  }]

  client_root_certificate = [{
    name             = null
    public_cert_data = null
  }]

  ipsec_policy = [{
    dh_group               = null
    ike_encryption         = null
    ike_integrity          = null
    ipsec_encryption       = null
    ipsec_integrity        = null
    pfs_group              = null
    sa_data_size_kilobytes = null
    sa_lifetime_seconds    = null
  }]

  radius = [{
    client_root_certificate = [{
      name       = null
      thumbprint = null
    }]
    server = [{
      address = null
      score   = null
      secret  = null
    }]
    server_root_certificate = [{
      name             = null
      public_cert_data = null
    }]
  }]

  radius_server = [{
    address = null
    client_root_certificate = [{
      name       = null
      thumbprint = null
    }]
    secret = null
    server_root_certificate = [{
      name             = null
      public_cert_data = null
    }]
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
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpn_authentication_types" {
  description = "(required)"
  type        = list(string)
}

variable "vpn_protocols" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "azure_active_directory_authentication" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      audience = string
      issuer   = string
      tenant   = string
    }
  ))
  default = []
}

variable "client_revoked_certificate" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name       = string
      thumbprint = string
    }
  ))
  default = []
}

variable "client_root_certificate" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name             = string
      public_cert_data = string
    }
  ))
  default = []
}

variable "ipsec_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      dh_group               = string
      ike_encryption         = string
      ike_integrity          = string
      ipsec_encryption       = string
      ipsec_integrity        = string
      pfs_group              = string
      sa_data_size_kilobytes = number
      sa_lifetime_seconds    = number
    }
  ))
  default = []
}

variable "radius" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_root_certificate = set(object(
        {
          name       = string
          thumbprint = string
        }
      ))
      server = list(object(
        {
          address = string
          score   = number
          secret  = string
        }
      ))
      server_root_certificate = set(object(
        {
          name             = string
          public_cert_data = string
        }
      ))
    }
  ))
  default = []
}

variable "radius_server" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address = string
      client_root_certificate = set(object(
        {
          name       = string
          thumbprint = string
        }
      ))
      secret = string
      server_root_certificate = set(object(
        {
          name             = string
          public_cert_data = string
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
```

[top](#index)

### Resource

```terraform
resource "azurerm_vpn_server_configuration" "this" {
  location                 = var.location
  name                     = var.name
  resource_group_name      = var.resource_group_name
  tags                     = var.tags
  vpn_authentication_types = var.vpn_authentication_types
  vpn_protocols            = var.vpn_protocols

  dynamic "azure_active_directory_authentication" {
    for_each = var.azure_active_directory_authentication
    content {
      audience = azure_active_directory_authentication.value["audience"]
      issuer   = azure_active_directory_authentication.value["issuer"]
      tenant   = azure_active_directory_authentication.value["tenant"]
    }
  }

  dynamic "client_revoked_certificate" {
    for_each = var.client_revoked_certificate
    content {
      name       = client_revoked_certificate.value["name"]
      thumbprint = client_revoked_certificate.value["thumbprint"]
    }
  }

  dynamic "client_root_certificate" {
    for_each = var.client_root_certificate
    content {
      name             = client_root_certificate.value["name"]
      public_cert_data = client_root_certificate.value["public_cert_data"]
    }
  }

  dynamic "ipsec_policy" {
    for_each = var.ipsec_policy
    content {
      dh_group               = ipsec_policy.value["dh_group"]
      ike_encryption         = ipsec_policy.value["ike_encryption"]
      ike_integrity          = ipsec_policy.value["ike_integrity"]
      ipsec_encryption       = ipsec_policy.value["ipsec_encryption"]
      ipsec_integrity        = ipsec_policy.value["ipsec_integrity"]
      pfs_group              = ipsec_policy.value["pfs_group"]
      sa_data_size_kilobytes = ipsec_policy.value["sa_data_size_kilobytes"]
      sa_lifetime_seconds    = ipsec_policy.value["sa_lifetime_seconds"]
    }
  }

  dynamic "radius" {
    for_each = var.radius
    content {

      dynamic "client_root_certificate" {
        for_each = radius.value.client_root_certificate
        content {
          name       = client_root_certificate.value["name"]
          thumbprint = client_root_certificate.value["thumbprint"]
        }
      }

      dynamic "server" {
        for_each = radius.value.server
        content {
          address = server.value["address"]
          score   = server.value["score"]
          secret  = server.value["secret"]
        }
      }

      dynamic "server_root_certificate" {
        for_each = radius.value.server_root_certificate
        content {
          name             = server_root_certificate.value["name"]
          public_cert_data = server_root_certificate.value["public_cert_data"]
        }
      }

    }
  }

  dynamic "radius_server" {
    for_each = var.radius_server
    content {
      address = radius_server.value["address"]
      secret  = radius_server.value["secret"]

      dynamic "client_root_certificate" {
        for_each = radius_server.value.client_root_certificate
        content {
          name       = client_root_certificate.value["name"]
          thumbprint = client_root_certificate.value["thumbprint"]
        }
      }

      dynamic "server_root_certificate" {
        for_each = radius_server.value.server_root_certificate
        content {
          name             = server_root_certificate.value["name"]
          public_cert_data = server_root_certificate.value["public_cert_data"]
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

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_vpn_server_configuration.this.id
}

output "vpn_protocols" {
  description = "returns a set of string"
  value       = azurerm_vpn_server_configuration.this.vpn_protocols
}

output "this" {
  value = azurerm_vpn_server_configuration.this
}
```

[top](#index)