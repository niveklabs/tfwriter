# azurerm_vpn_gateway_connection

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
module "azurerm_vpn_gateway_connection" {
  source = "./modules/azurerm/r/azurerm_vpn_gateway_connection"

  # internet_security_enabled - (optional) is a type of bool
  internet_security_enabled = null
  # name - (required) is a type of string
  name = null
  # remote_vpn_site_id - (required) is a type of string
  remote_vpn_site_id = null
  # vpn_gateway_id - (required) is a type of string
  vpn_gateway_id = null

  routing = [{
    associated_route_table  = null
    propagated_route_tables = []
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  vpn_link = [{
    bandwidth_mbps = null
    bgp_enabled    = null
    ipsec_policy = [{
      dh_group                 = null
      encryption_algorithm     = null
      ike_encryption_algorithm = null
      ike_integrity_algorithm  = null
      integrity_algorithm      = null
      pfs_group                = null
      sa_data_size_kb          = null
      sa_lifetime_sec          = null
    }]
    local_azure_ip_address_enabled        = null
    name                                  = null
    policy_based_traffic_selector_enabled = null
    protocol                              = null
    ratelimit_enabled                     = null
    route_weight                          = null
    shared_key                            = null
    vpn_site_link_id                      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "internet_security_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "remote_vpn_site_id" {
  description = "(required)"
  type        = string
}

variable "vpn_gateway_id" {
  description = "(required)"
  type        = string
}

variable "routing" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      associated_route_table  = string
      propagated_route_tables = list(string)
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

variable "vpn_link" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      bandwidth_mbps = number
      bgp_enabled    = bool
      ipsec_policy = list(object(
        {
          dh_group                 = string
          encryption_algorithm     = string
          ike_encryption_algorithm = string
          ike_integrity_algorithm  = string
          integrity_algorithm      = string
          pfs_group                = string
          sa_data_size_kb          = number
          sa_lifetime_sec          = number
        }
      ))
      local_azure_ip_address_enabled        = bool
      name                                  = string
      policy_based_traffic_selector_enabled = bool
      protocol                              = string
      ratelimit_enabled                     = bool
      route_weight                          = number
      shared_key                            = string
      vpn_site_link_id                      = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_vpn_gateway_connection" "this" {
  internet_security_enabled = var.internet_security_enabled
  name                      = var.name
  remote_vpn_site_id        = var.remote_vpn_site_id
  vpn_gateway_id            = var.vpn_gateway_id

  dynamic "routing" {
    for_each = var.routing
    content {
      associated_route_table  = routing.value["associated_route_table"]
      propagated_route_tables = routing.value["propagated_route_tables"]
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

  dynamic "vpn_link" {
    for_each = var.vpn_link
    content {
      bandwidth_mbps                        = vpn_link.value["bandwidth_mbps"]
      bgp_enabled                           = vpn_link.value["bgp_enabled"]
      local_azure_ip_address_enabled        = vpn_link.value["local_azure_ip_address_enabled"]
      name                                  = vpn_link.value["name"]
      policy_based_traffic_selector_enabled = vpn_link.value["policy_based_traffic_selector_enabled"]
      protocol                              = vpn_link.value["protocol"]
      ratelimit_enabled                     = vpn_link.value["ratelimit_enabled"]
      route_weight                          = vpn_link.value["route_weight"]
      shared_key                            = vpn_link.value["shared_key"]
      vpn_site_link_id                      = vpn_link.value["vpn_site_link_id"]

      dynamic "ipsec_policy" {
        for_each = vpn_link.value.ipsec_policy
        content {
          dh_group                 = ipsec_policy.value["dh_group"]
          encryption_algorithm     = ipsec_policy.value["encryption_algorithm"]
          ike_encryption_algorithm = ipsec_policy.value["ike_encryption_algorithm"]
          ike_integrity_algorithm  = ipsec_policy.value["ike_integrity_algorithm"]
          integrity_algorithm      = ipsec_policy.value["integrity_algorithm"]
          pfs_group                = ipsec_policy.value["pfs_group"]
          sa_data_size_kb          = ipsec_policy.value["sa_data_size_kb"]
          sa_lifetime_sec          = ipsec_policy.value["sa_lifetime_sec"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_vpn_gateway_connection.this.id
}

output "this" {
  value = azurerm_vpn_gateway_connection.this
}
```

[top](#index)