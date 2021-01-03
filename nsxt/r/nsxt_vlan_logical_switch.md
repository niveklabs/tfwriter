# nsxt_vlan_logical_switch

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
module "nsxt_vlan_logical_switch" {
  source = "./modules/nsxt/r/nsxt_vlan_logical_switch"

  # admin_state - (optional) is a type of string
  admin_state = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # ip_pool_id - (optional) is a type of string
  ip_pool_id = null
  # mac_pool_id - (optional) is a type of string
  mac_pool_id = null
  # transport_zone_id - (required) is a type of string
  transport_zone_id = null
  # vlan - (required) is a type of number
  vlan = null

  address_binding = [{
    ip_address  = null
    mac_address = null
    vlan        = null
  }]

  switching_profile_id = [{
    key   = null
    value = null
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
variable "admin_state" {
  description = "(optional) - Represents Desired state of the object"
  type        = string
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

variable "ip_pool_id" {
  description = "(optional) - IP pool id that associated with a LogicalSwitch"
  type        = string
  default     = null
}

variable "mac_pool_id" {
  description = "(optional) - Mac pool id that associated with a LogicalSwitch"
  type        = string
  default     = null
}

variable "transport_zone_id" {
  description = "(required) - Id of the TransportZone to which this LogicalSwitch is associated"
  type        = string
}

variable "vlan" {
  description = "(required) - VLAN Id"
  type        = number
}

variable "address_binding" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip_address  = string
      mac_address = string
      vlan        = number
    }
  ))
  default = []
}

variable "switching_profile_id" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
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
resource "nsxt_vlan_logical_switch" "this" {
  admin_state       = var.admin_state
  description       = var.description
  display_name      = var.display_name
  ip_pool_id        = var.ip_pool_id
  mac_pool_id       = var.mac_pool_id
  transport_zone_id = var.transport_zone_id
  vlan              = var.vlan

  dynamic "address_binding" {
    for_each = var.address_binding
    content {
      ip_address  = address_binding.value["ip_address"]
      mac_address = address_binding.value["mac_address"]
      vlan        = address_binding.value["vlan"]
    }
  }

  dynamic "switching_profile_id" {
    for_each = var.switching_profile_id
    content {
      key   = switching_profile_id.value["key"]
      value = switching_profile_id.value["value"]
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
  value       = nsxt_vlan_logical_switch.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_vlan_logical_switch.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_vlan_logical_switch.this.revision
}

output "this" {
  value = nsxt_vlan_logical_switch.this
}
```

[top](#index)