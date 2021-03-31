# nsxt_policy_ip_pool_static_subnet

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
module "nsxt_policy_ip_pool_static_subnet" {
  source = "./modules/nsxt/r/nsxt_policy_ip_pool_static_subnet"

  # cidr - (required) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # dns_nameservers - (optional) is a type of list of string
  dns_nameservers = []
  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # gateway - (optional) is a type of string
  gateway = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # pool_path - (required) is a type of string
  pool_path = null

  allocation_range = [{
    end   = null
    start = null
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
variable "cidr" {
  description = "(required) - Network address and prefix length"
  type        = string
}

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
  description = "(optional) - The collection of up to 3 DNS servers for the subnet"
  type        = list(string)
  default     = null
}

variable "dns_suffix" {
  description = "(optional) - DNS suffix for the nameserver"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(optional) - The default gateway address"
  type        = string
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "pool_path" {
  description = "(required) - Policy path to the IP Pool for this Subnet"
  type        = string
}

variable "allocation_range" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      end   = string
      start = string
    }
  ))
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
resource "nsxt_policy_ip_pool_static_subnet" "this" {
  cidr            = var.cidr
  description     = var.description
  display_name    = var.display_name
  dns_nameservers = var.dns_nameservers
  dns_suffix      = var.dns_suffix
  gateway         = var.gateway
  nsx_id          = var.nsx_id
  pool_path       = var.pool_path

  dynamic "allocation_range" {
    for_each = var.allocation_range
    content {
      end   = allocation_range.value["end"]
      start = allocation_range.value["start"]
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
  value       = nsxt_policy_ip_pool_static_subnet.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_ip_pool_static_subnet.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_ip_pool_static_subnet.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_ip_pool_static_subnet.this.revision
}

output "this" {
  value = nsxt_policy_ip_pool_static_subnet.this
}
```

[top](#index)