# nsxt_policy_dhcp_v4_static_binding

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_dhcp_v4_static_binding" {
  source = "./modules/nsxt/r/nsxt_policy_dhcp_v4_static_binding"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # gateway_address - (optional) is a type of string
  gateway_address = null
  # hostname - (optional) is a type of string
  hostname = null
  # ip_address - (required) is a type of string
  ip_address = null
  # lease_time - (optional) is a type of number
  lease_time = null
  # mac_address - (required) is a type of string
  mac_address = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # segment_path - (required) is a type of string
  segment_path = null

  dhcp_generic_option = [{
    code   = null
    values = []
  }]

  dhcp_option_121 = [{
    network  = null
    next_hop = null
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

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "gateway_address" {
  description = "(optional) - When not specified, gateway address is auto-assigned from segment configuration"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional) - Hostname to assign to the host"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(required) - IP assigned to host. The IP address must belong to the subnetconfigured on segment"
  type        = string
}

variable "lease_time" {
  description = "(optional) - DHCP lease time in seconds"
  type        = number
  default     = null
}

variable "mac_address" {
  description = "(required) - MAC address of the host"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "segment_path" {
  description = "(required) - segment path"
  type        = string
}

variable "dhcp_generic_option" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      code   = number
      values = list(string)
    }
  ))
  default = []
}

variable "dhcp_option_121" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      network  = string
      next_hop = string
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
resource "nsxt_policy_dhcp_v4_static_binding" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # gateway_address - (optional) is a type of string
  gateway_address = var.gateway_address
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # ip_address - (required) is a type of string
  ip_address = var.ip_address
  # lease_time - (optional) is a type of number
  lease_time = var.lease_time
  # mac_address - (required) is a type of string
  mac_address = var.mac_address
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # segment_path - (required) is a type of string
  segment_path = var.segment_path

  dynamic "dhcp_generic_option" {
    for_each = var.dhcp_generic_option
    content {
      # code - (required) is a type of number
      code = dhcp_generic_option.value["code"]
      # values - (required) is a type of list of string
      values = dhcp_generic_option.value["values"]
    }
  }

  dynamic "dhcp_option_121" {
    for_each = var.dhcp_option_121
    content {
      # network - (required) is a type of string
      network = dhcp_option_121.value["network"]
      # next_hop - (required) is a type of string
      next_hop = dhcp_option_121.value["next_hop"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_v4_static_binding.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_v4_static_binding.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_v4_static_binding.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_dhcp_v4_static_binding.this.revision
}

output "this" {
  value = nsxt_policy_dhcp_v4_static_binding.this
}
```

[top](#index)