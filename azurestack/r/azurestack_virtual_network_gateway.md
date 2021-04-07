# azurestack_virtual_network_gateway

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_virtual_network_gateway" {
  source = "./modules/azurestack/r/azurestack_virtual_network_gateway"

  # default_local_network_gateway_id - (optional) is a type of string
  default_local_network_gateway_id = null
  # enable_bgp - (optional) is a type of bool
  enable_bgp = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sku - (required) is a type of string
  sku = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
  # vpn_type - (optional) is a type of string
  vpn_type = null

  bgp_settings = [{
    asn             = null
    peer_weight     = null
    peering_address = null
  }]

  ip_configuration = [{
    name                          = null
    private_ip_address_allocation = null
    public_ip_address_id          = null
    subnet_id                     = null
  }]

  vpn_client_configuration = [{
    address_space = []
    revoked_certificate = [{
      name       = null
      thumbprint = null
    }]
    root_certificate = [{
      name             = null
      public_cert_data = null
    }]
    vpn_client_protocols = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_local_network_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_bgp" {
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

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sku" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "vpn_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      asn             = number
      peer_weight     = number
      peering_address = string
    }
  ))
  default = []
}

variable "ip_configuration" {
  description = "nested block: NestingList, min items: 1, max items: 2"
  type = set(object(
    {
      name                          = string
      private_ip_address_allocation = string
      public_ip_address_id          = string
      subnet_id                     = string
    }
  ))
}

variable "vpn_client_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address_space = list(string)
      revoked_certificate = set(object(
        {
          name       = string
          thumbprint = string
        }
      ))
      root_certificate = set(object(
        {
          name             = string
          public_cert_data = string
        }
      ))
      vpn_client_protocols = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_virtual_network_gateway" "this" {
  # default_local_network_gateway_id - (optional) is a type of string
  default_local_network_gateway_id = var.default_local_network_gateway_id
  # enable_bgp - (optional) is a type of bool
  enable_bgp = var.enable_bgp
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # sku - (required) is a type of string
  sku = var.sku
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
  # vpn_type - (optional) is a type of string
  vpn_type = var.vpn_type

  dynamic "bgp_settings" {
    for_each = var.bgp_settings
    content {
      # asn - (optional) is a type of number
      asn = bgp_settings.value["asn"]
      # peer_weight - (optional) is a type of number
      peer_weight = bgp_settings.value["peer_weight"]
      # peering_address - (optional) is a type of string
      peering_address = bgp_settings.value["peering_address"]
    }
  }

  dynamic "ip_configuration" {
    for_each = var.ip_configuration
    content {
      # name - (optional) is a type of string
      name = ip_configuration.value["name"]
      # private_ip_address_allocation - (optional) is a type of string
      private_ip_address_allocation = ip_configuration.value["private_ip_address_allocation"]
      # public_ip_address_id - (optional) is a type of string
      public_ip_address_id = ip_configuration.value["public_ip_address_id"]
      # subnet_id - (required) is a type of string
      subnet_id = ip_configuration.value["subnet_id"]
    }
  }

  dynamic "vpn_client_configuration" {
    for_each = var.vpn_client_configuration
    content {
      # address_space - (required) is a type of list of string
      address_space = vpn_client_configuration.value["address_space"]
      # vpn_client_protocols - (optional) is a type of set of string
      vpn_client_protocols = vpn_client_configuration.value["vpn_client_protocols"]

      dynamic "revoked_certificate" {
        for_each = vpn_client_configuration.value.revoked_certificate
        content {
          # name - (required) is a type of string
          name = revoked_certificate.value["name"]
          # thumbprint - (required) is a type of string
          thumbprint = revoked_certificate.value["thumbprint"]
        }
      }

      dynamic "root_certificate" {
        for_each = vpn_client_configuration.value.root_certificate
        content {
          # name - (required) is a type of string
          name = root_certificate.value["name"]
          # public_cert_data - (required) is a type of string
          public_cert_data = root_certificate.value["public_cert_data"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "enable_bgp" {
  description = "returns a bool"
  value       = azurestack_virtual_network_gateway.this.enable_bgp
}

output "id" {
  description = "returns a string"
  value       = azurestack_virtual_network_gateway.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_virtual_network_gateway.this.tags
}

output "this" {
  value = azurestack_virtual_network_gateway.this
}
```

[top](#index)