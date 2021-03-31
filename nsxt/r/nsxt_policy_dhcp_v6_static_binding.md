# nsxt_policy_dhcp_v6_static_binding

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
module "nsxt_policy_dhcp_v6_static_binding" {
  source = "./modules/nsxt/r/nsxt_policy_dhcp_v6_static_binding"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # dns_nameservers - (optional) is a type of list of string
  dns_nameservers = []
  # domain_names - (optional) is a type of list of string
  domain_names = []
  # ip_addresses - (optional) is a type of list of string
  ip_addresses = []
  # lease_time - (optional) is a type of number
  lease_time = null
  # mac_address - (required) is a type of string
  mac_address = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # preferred_time - (optional) is a type of number
  preferred_time = null
  # segment_path - (required) is a type of string
  segment_path = null
  # sntp_servers - (optional) is a type of list of string
  sntp_servers = []

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

variable "dns_nameservers" {
  description = "(optional) - DNS nameservers"
  type        = list(string)
  default     = null
}

variable "domain_names" {
  description = "(optional) - Domain names"
  type        = list(string)
  default     = null
}

variable "ip_addresses" {
  description = "(optional) - IP addresses"
  type        = list(string)
  default     = null
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

variable "preferred_time" {
  description = "(optional) - The time interval in seconds, in which the prefix is advertised as preferred"
  type        = number
  default     = null
}

variable "segment_path" {
  description = "(required) - segment path"
  type        = string
}

variable "sntp_servers" {
  description = "(optional) - SNTP server IP addresses"
  type        = list(string)
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
resource "nsxt_policy_dhcp_v6_static_binding" "this" {
  description     = var.description
  display_name    = var.display_name
  dns_nameservers = var.dns_nameservers
  domain_names    = var.domain_names
  ip_addresses    = var.ip_addresses
  lease_time      = var.lease_time
  mac_address     = var.mac_address
  nsx_id          = var.nsx_id
  preferred_time  = var.preferred_time
  segment_path    = var.segment_path
  sntp_servers    = var.sntp_servers

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
  value       = nsxt_policy_dhcp_v6_static_binding.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_v6_static_binding.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_v6_static_binding.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_dhcp_v6_static_binding.this.revision
}

output "this" {
  value = nsxt_policy_dhcp_v6_static_binding.this
}
```

[top](#index)