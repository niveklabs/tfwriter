# nsxt_policy_tier1_gateway_interface

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
module "nsxt_policy_tier1_gateway_interface" {
  source = "./modules/nsxt/r/nsxt_policy_tier1_gateway_interface"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # gateway_path - (required) is a type of string
  gateway_path = null
  # ipv6_ndra_profile_path - (optional) is a type of string
  ipv6_ndra_profile_path = null
  # mtu - (optional) is a type of number
  mtu = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # segment_path - (required) is a type of string
  segment_path = null
  # site_path - (optional) is a type of string
  site_path = null
  # subnets - (required) is a type of list of string
  subnets = []
  # urpf_mode - (optional) is a type of string
  urpf_mode = null

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

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "gateway_path" {
  description = "(required) - Policy path for tier1 gateway"
  type        = string
}

variable "ipv6_ndra_profile_path" {
  description = "(optional) - The path of an IPv6 NDRA profile"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - Maximum transmission unit specifies the size of the largest packet that a network protocol can transmit"
  type        = number
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "segment_path" {
  description = "(required) - Policy path for connected segment"
  type        = string
}

variable "site_path" {
  description = "(optional) - Path of the site the Tier1 edge cluster belongs to"
  type        = string
  default     = null
}

variable "subnets" {
  description = "(required) - List of IP addresses and network prefixes for this interface"
  type        = list(string)
}

variable "urpf_mode" {
  description = "(optional) - Unicast Reverse Path Forwarding mode"
  type        = string
  default     = null
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
resource "nsxt_policy_tier1_gateway_interface" "this" {
  description            = var.description
  display_name           = var.display_name
  gateway_path           = var.gateway_path
  ipv6_ndra_profile_path = var.ipv6_ndra_profile_path
  mtu                    = var.mtu
  nsx_id                 = var.nsx_id
  segment_path           = var.segment_path
  site_path              = var.site_path
  subnets                = var.subnets
  urpf_mode              = var.urpf_mode

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
  value       = nsxt_policy_tier1_gateway_interface.this.id
}

output "ipv6_ndra_profile_path" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway_interface.this.ipv6_ndra_profile_path
}

output "locale_service_id" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway_interface.this.locale_service_id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway_interface.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_tier1_gateway_interface.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_tier1_gateway_interface.this.revision
}

output "this" {
  value = nsxt_policy_tier1_gateway_interface.this
}
```

[top](#index)