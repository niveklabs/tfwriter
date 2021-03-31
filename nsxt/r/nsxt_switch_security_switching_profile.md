# nsxt_switch_security_switching_profile

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
module "nsxt_switch_security_switching_profile" {
  source = "./modules/nsxt/r/nsxt_switch_security_switching_profile"

  # block_client_dhcp - (optional) is a type of bool
  block_client_dhcp = null
  # block_non_ip - (optional) is a type of bool
  block_non_ip = null
  # block_server_dhcp - (optional) is a type of bool
  block_server_dhcp = null
  # bpdu_filter_enabled - (optional) is a type of bool
  bpdu_filter_enabled = null
  # bpdu_filter_whitelist - (optional) is a type of set of string
  bpdu_filter_whitelist = []
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null

  rate_limits = [{
    enabled      = null
    rx_broadcast = null
    rx_multicast = null
    tx_broadcast = null
    tx_multicast = null
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
variable "block_client_dhcp" {
  description = "(optional) - Indicates whether DHCP client blocking is enabled"
  type        = bool
  default     = null
}

variable "block_non_ip" {
  description = "(optional) - Block all traffic except IP/(G)ARP/BPDU"
  type        = bool
  default     = null
}

variable "block_server_dhcp" {
  description = "(optional) - Indicates whether DHCP server blocking is enabled"
  type        = bool
  default     = null
}

variable "bpdu_filter_enabled" {
  description = "(optional) - Indicates whether BPDU filter is enabled"
  type        = bool
  default     = null
}

variable "bpdu_filter_whitelist" {
  description = "(optional) - Set of allowed MAC addresses to be excluded from BPDU filtering"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "rate_limits" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled      = bool
      rx_broadcast = number
      rx_multicast = number
      tx_broadcast = number
      tx_multicast = number
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
resource "nsxt_switch_security_switching_profile" "this" {
  block_client_dhcp     = var.block_client_dhcp
  block_non_ip          = var.block_non_ip
  block_server_dhcp     = var.block_server_dhcp
  bpdu_filter_enabled   = var.bpdu_filter_enabled
  bpdu_filter_whitelist = var.bpdu_filter_whitelist
  description           = var.description
  display_name          = var.display_name

  dynamic "rate_limits" {
    for_each = var.rate_limits
    content {
      enabled      = rate_limits.value["enabled"]
      rx_broadcast = rate_limits.value["rx_broadcast"]
      rx_multicast = rate_limits.value["rx_multicast"]
      tx_broadcast = rate_limits.value["tx_broadcast"]
      tx_multicast = rate_limits.value["tx_multicast"]
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
output "display_name" {
  description = "returns a string"
  value       = nsxt_switch_security_switching_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_switch_security_switching_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_switch_security_switching_profile.this.revision
}

output "this" {
  value = nsxt_switch_security_switching_profile.this
}
```

[top](#index)