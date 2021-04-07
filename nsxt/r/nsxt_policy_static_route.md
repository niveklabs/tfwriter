# nsxt_policy_static_route

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
module "nsxt_policy_static_route" {
  source = "./modules/nsxt/r/nsxt_policy_static_route"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # gateway_path - (required) is a type of string
  gateway_path = null
  # network - (required) is a type of string
  network = null
  # nsx_id - (optional) is a type of string
  nsx_id = null

  next_hop = [{
    admin_distance = null
    interface      = null
    ip_address     = null
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

variable "gateway_path" {
  description = "(required) - The NSX-T Policy path to the Tier0 or Tier1 Gateway for this resource"
  type        = string
}

variable "network" {
  description = "(required) - Network address in CIDR format"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "next_hop" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      admin_distance = number
      interface      = string
      ip_address     = string
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
resource "nsxt_policy_static_route" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # gateway_path - (required) is a type of string
  gateway_path = var.gateway_path
  # network - (required) is a type of string
  network = var.network
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id

  dynamic "next_hop" {
    for_each = var.next_hop
    content {
      # admin_distance - (optional) is a type of number
      admin_distance = next_hop.value["admin_distance"]
      # interface - (optional) is a type of string
      interface = next_hop.value["interface"]
      # ip_address - (required) is a type of string
      ip_address = next_hop.value["ip_address"]
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
  value       = nsxt_policy_static_route.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_static_route.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_static_route.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_static_route.this.revision
}

output "this" {
  value = nsxt_policy_static_route.this
}
```

[top](#index)