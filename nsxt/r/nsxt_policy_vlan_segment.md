# nsxt_policy_vlan_segment

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_vlan_segment" {
  source = "./modules/nsxt/r/nsxt_policy_vlan_segment"

  # description - (optional) is a type of string
  description = null
  # dhcp_config_path - (optional) is a type of string
  dhcp_config_path = null
  # display_name - (required) is a type of string
  display_name = null
  # domain_name - (optional) is a type of string
  domain_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # transport_zone_path - (required) is a type of string
  transport_zone_path = null
  # vlan_ids - (required) is a type of list of string
  vlan_ids = []

  advanced_config = [{
    address_pool_path     = null
    connectivity          = null
    hybrid                = null
    local_egress          = null
    uplink_teaming_policy = null
  }]

  discovery_profile = [{
    binding_map_path           = null
    ip_discovery_profile_path  = null
    mac_discovery_profile_path = null
    revision                   = null
  }]

  l2_extension = [{
    l2vpn_paths = []
    tunnel_id   = null
  }]

  qos_profile = [{
    binding_map_path = null
    qos_profile_path = null
    revision         = null
  }]

  security_profile = [{
    binding_map_path        = null
    revision                = null
    security_profile_path   = null
    spoofguard_profile_path = null
  }]

  subnet = [{
    cidr        = null
    dhcp_ranges = []
    dhcp_v4_config = [{
      dhcp_generic_option = [{
        code   = null
        values = []
      }]
      dhcp_option_121 = [{
        network  = null
        next_hop = null
      }]
      dns_servers    = []
      lease_time     = null
      server_address = null
    }]
    dhcp_v6_config = [{
      dns_servers  = []
      domain_names = []
      excluded_range = [{
        end   = null
        start = null
      }]
      lease_time     = null
      preferred_time = null
      server_address = null
      sntp_servers   = []
    }]
    network = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "dhcp_config_path" {
  description = "(optional) - Policy path to DHCP server or relay configuration to use for subnets configured on this segment"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "domain_name" {
  description = "(optional) - DNS domain names"
  type        = string
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "transport_zone_path" {
  description = "(required) - Policy path to the transport zone"
  type        = string
}

variable "vlan_ids" {
  description = "(required) - VLAN IDs for VLAN backed Segment"
  type        = list(string)
}

variable "advanced_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address_pool_path     = string
      connectivity          = string
      hybrid                = bool
      local_egress          = bool
      uplink_teaming_policy = string
    }
  ))
  default = []
}

variable "discovery_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      binding_map_path           = string
      ip_discovery_profile_path  = string
      mac_discovery_profile_path = string
      revision                   = number
    }
  ))
  default = []
}

variable "l2_extension" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      l2vpn_paths = list(string)
      tunnel_id   = number
    }
  ))
  default = []
}

variable "qos_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      binding_map_path = string
      qos_profile_path = string
      revision         = number
    }
  ))
  default = []
}

variable "security_profile" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      binding_map_path        = string
      revision                = number
      security_profile_path   = string
      spoofguard_profile_path = string
    }
  ))
  default = []
}

variable "subnet" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cidr        = string
      dhcp_ranges = list(string)
      dhcp_v4_config = list(object(
        {
          dhcp_generic_option = list(object(
            {
              code   = number
              values = list(string)
            }
          ))
          dhcp_option_121 = list(object(
            {
              network  = string
              next_hop = string
            }
          ))
          dns_servers    = list(string)
          lease_time     = number
          server_address = string
        }
      ))
      dhcp_v6_config = list(object(
        {
          dns_servers  = list(string)
          domain_names = list(string)
          excluded_range = list(object(
            {
              end   = string
              start = string
            }
          ))
          lease_time     = number
          preferred_time = number
          server_address = string
          sntp_servers   = list(string)
        }
      ))
      network = string
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_policy_vlan_segment" "this" {
  description         = var.description
  dhcp_config_path    = var.dhcp_config_path
  display_name        = var.display_name
  domain_name         = var.domain_name
  nsx_id              = var.nsx_id
  transport_zone_path = var.transport_zone_path
  vlan_ids            = var.vlan_ids

  dynamic "advanced_config" {
    for_each = var.advanced_config
    content {
      address_pool_path     = advanced_config.value["address_pool_path"]
      connectivity          = advanced_config.value["connectivity"]
      hybrid                = advanced_config.value["hybrid"]
      local_egress          = advanced_config.value["local_egress"]
      uplink_teaming_policy = advanced_config.value["uplink_teaming_policy"]
    }
  }

  dynamic "discovery_profile" {
    for_each = var.discovery_profile
    content {
      binding_map_path           = discovery_profile.value["binding_map_path"]
      ip_discovery_profile_path  = discovery_profile.value["ip_discovery_profile_path"]
      mac_discovery_profile_path = discovery_profile.value["mac_discovery_profile_path"]
    }
  }

  dynamic "l2_extension" {
    for_each = var.l2_extension
    content {
      l2vpn_paths = l2_extension.value["l2vpn_paths"]
      tunnel_id   = l2_extension.value["tunnel_id"]
    }
  }

  dynamic "qos_profile" {
    for_each = var.qos_profile
    content {
      binding_map_path = qos_profile.value["binding_map_path"]
      qos_profile_path = qos_profile.value["qos_profile_path"]
    }
  }

  dynamic "security_profile" {
    for_each = var.security_profile
    content {
      binding_map_path        = security_profile.value["binding_map_path"]
      security_profile_path   = security_profile.value["security_profile_path"]
      spoofguard_profile_path = security_profile.value["spoofguard_profile_path"]
    }
  }

  dynamic "subnet" {
    for_each = var.subnet
    content {
      cidr        = subnet.value["cidr"]
      dhcp_ranges = subnet.value["dhcp_ranges"]

      dynamic "dhcp_v4_config" {
        for_each = subnet.value.dhcp_v4_config
        content {
          dns_servers    = dhcp_v4_config.value["dns_servers"]
          lease_time     = dhcp_v4_config.value["lease_time"]
          server_address = dhcp_v4_config.value["server_address"]

          dynamic "dhcp_generic_option" {
            for_each = dhcp_v4_config.value.dhcp_generic_option
            content {
              code   = dhcp_generic_option.value["code"]
              values = dhcp_generic_option.value["values"]
            }
          }

          dynamic "dhcp_option_121" {
            for_each = dhcp_v4_config.value.dhcp_option_121
            content {
              network  = dhcp_option_121.value["network"]
              next_hop = dhcp_option_121.value["next_hop"]
            }
          }

        }
      }

      dynamic "dhcp_v6_config" {
        for_each = subnet.value.dhcp_v6_config
        content {
          dns_servers    = dhcp_v6_config.value["dns_servers"]
          domain_names   = dhcp_v6_config.value["domain_names"]
          lease_time     = dhcp_v6_config.value["lease_time"]
          preferred_time = dhcp_v6_config.value["preferred_time"]
          server_address = dhcp_v6_config.value["server_address"]
          sntp_servers   = dhcp_v6_config.value["sntp_servers"]

          dynamic "excluded_range" {
            for_each = dhcp_v6_config.value.excluded_range
            content {
              end   = excluded_range.value["end"]
              start = excluded_range.value["start"]
            }
          }

        }
      }

    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_vlan_segment.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_vlan_segment.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_vlan_segment.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_vlan_segment.this.revision
}

output "this" {
  value = nsxt_policy_vlan_segment.this
}
```

[top](#index)