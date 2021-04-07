# avi_network

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_network" {
  source = "./modules/avi/r/avi_network"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # dhcp_enabled - (optional) is a type of bool
  dhcp_enabled = null
  # exclude_discovered_subnets - (optional) is a type of bool
  exclude_discovered_subnets = null
  # ip6_autocfg_enabled - (optional) is a type of bool
  ip6_autocfg_enabled = null
  # name - (required) is a type of string
  name = null
  # synced_from_se - (optional) is a type of bool
  synced_from_se = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # vcenter_dvs - (optional) is a type of bool
  vcenter_dvs = null
  # vrf_context_ref - (optional) is a type of string
  vrf_context_ref = null

  configured_subnets = [{
    prefix = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    static_ips = [{
      addr = null
      type = null
    }]
    static_ranges = [{
      begin = [{
        addr = null
        type = null
      }]
      end = [{
        addr = null
        type = null
      }]
    }]
  }]

  labels = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_discovered_subnets" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip6_autocfg_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "synced_from_se" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcenter_dvs" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vrf_context_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configured_subnets" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      prefix = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      static_ips = list(object(
        {
          addr = string
          type = string
        }
      ))
      static_ranges = list(object(
        {
          begin = set(object(
            {
              addr = string
              type = string
            }
          ))
          end = set(object(
            {
              addr = string
              type = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "labels" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_network" "this" {
  # cloud_ref - (optional) is a type of string
  cloud_ref = var.cloud_ref
  # dhcp_enabled - (optional) is a type of bool
  dhcp_enabled = var.dhcp_enabled
  # exclude_discovered_subnets - (optional) is a type of bool
  exclude_discovered_subnets = var.exclude_discovered_subnets
  # ip6_autocfg_enabled - (optional) is a type of bool
  ip6_autocfg_enabled = var.ip6_autocfg_enabled
  # name - (required) is a type of string
  name = var.name
  # synced_from_se - (optional) is a type of bool
  synced_from_se = var.synced_from_se
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vcenter_dvs - (optional) is a type of bool
  vcenter_dvs = var.vcenter_dvs
  # vrf_context_ref - (optional) is a type of string
  vrf_context_ref = var.vrf_context_ref

  dynamic "configured_subnets" {
    for_each = var.configured_subnets
    content {

      dynamic "prefix" {
        for_each = configured_subnets.value.prefix
        content {
          # mask - (required) is a type of number
          mask = prefix.value["mask"]

          dynamic "ip_addr" {
            for_each = prefix.value.ip_addr
            content {
              # addr - (required) is a type of string
              addr = ip_addr.value["addr"]
              # type - (required) is a type of string
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "static_ips" {
        for_each = configured_subnets.value.static_ips
        content {
          # addr - (required) is a type of string
          addr = static_ips.value["addr"]
          # type - (required) is a type of string
          type = static_ips.value["type"]
        }
      }

      dynamic "static_ranges" {
        for_each = configured_subnets.value.static_ranges
        content {

          dynamic "begin" {
            for_each = static_ranges.value.begin
            content {
              # addr - (required) is a type of string
              addr = begin.value["addr"]
              # type - (required) is a type of string
              type = begin.value["type"]
            }
          }

          dynamic "end" {
            for_each = static_ranges.value.end
            content {
              # addr - (required) is a type of string
              addr = end.value["addr"]
              # type - (required) is a type of string
              type = end.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "labels" {
    for_each = var.labels
    content {
      # key - (required) is a type of string
      key = labels.value["key"]
      # value - (optional) is a type of string
      value = labels.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = avi_network.this.cloud_ref
}

output "id" {
  description = "returns a string"
  value       = avi_network.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_network.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_network.this.uuid
}

output "vrf_context_ref" {
  description = "returns a string"
  value       = avi_network.this.vrf_context_ref
}

output "this" {
  value = avi_network.this
}
```

[top](#index)