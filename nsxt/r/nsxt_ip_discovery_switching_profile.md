# nsxt_ip_discovery_switching_profile

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
module "nsxt_ip_discovery_switching_profile" {
  source = "./modules/nsxt/r/nsxt_ip_discovery_switching_profile"

  # arp_bindings_limit - (optional) is a type of number
  arp_bindings_limit = null
  # arp_snooping_enabled - (optional) is a type of bool
  arp_snooping_enabled = null
  # description - (optional) is a type of string
  description = null
  # dhcp_snooping_enabled - (optional) is a type of bool
  dhcp_snooping_enabled = null
  # display_name - (optional) is a type of string
  display_name = null
  # vm_tools_enabled - (optional) is a type of bool
  vm_tools_enabled = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "arp_bindings_limit" {
  description = "(optional) - Limit for the amount of ARP bindings"
  type        = number
  default     = null
}

variable "arp_snooping_enabled" {
  description = "(optional) - Indicates whether ARP snooping is enabled"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "dhcp_snooping_enabled" {
  description = "(optional) - Indicates whether DHCP snooping is enabled"
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "vm_tools_enabled" {
  description = "(optional) - Indicating whether VM tools will be enabled. This option is only supported on ESX where vm-tools is installed"
  type        = bool
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
resource "nsxt_ip_discovery_switching_profile" "this" {
  arp_bindings_limit    = var.arp_bindings_limit
  arp_snooping_enabled  = var.arp_snooping_enabled
  description           = var.description
  dhcp_snooping_enabled = var.dhcp_snooping_enabled
  display_name          = var.display_name
  vm_tools_enabled      = var.vm_tools_enabled

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
  value       = nsxt_ip_discovery_switching_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_ip_discovery_switching_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_ip_discovery_switching_profile.this.revision
}

output "this" {
  value = nsxt_ip_discovery_switching_profile.this
}
```

[top](#index)