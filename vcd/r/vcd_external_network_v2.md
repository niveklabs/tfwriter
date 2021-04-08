# vcd_external_network_v2

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_external_network_v2" {
  source = "./modules/vcd/r/vcd_external_network_v2"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  ip_scope = [{
    dns1          = null
    dns2          = null
    dns_suffix    = null
    enabled       = null
    gateway       = null
    prefix_length = null
    static_ip_pool = [{
      end_address   = null
      start_address = null
    }]
  }]

  nsxt_network = [{
    nsxt_manager_id      = null
    nsxt_tier0_router_id = null
  }]

  vsphere_network = [{
    portgroup_id = null
    vcenter_id   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Network description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Network name"
  type        = string
}

variable "ip_scope" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      dns1          = string
      dns2          = string
      dns_suffix    = string
      enabled       = bool
      gateway       = string
      prefix_length = number
      static_ip_pool = set(object(
        {
          end_address   = string
          start_address = string
        }
      ))
    }
  ))
}

variable "nsxt_network" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      nsxt_manager_id      = string
      nsxt_tier0_router_id = string
    }
  ))
  default = []
}

variable "vsphere_network" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      portgroup_id = string
      vcenter_id   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_external_network_v2" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "ip_scope" {
    for_each = var.ip_scope
    content {
      # dns1 - (optional) is a type of string
      dns1 = ip_scope.value["dns1"]
      # dns2 - (optional) is a type of string
      dns2 = ip_scope.value["dns2"]
      # dns_suffix - (optional) is a type of string
      dns_suffix = ip_scope.value["dns_suffix"]
      # enabled - (optional) is a type of bool
      enabled = ip_scope.value["enabled"]
      # gateway - (required) is a type of string
      gateway = ip_scope.value["gateway"]
      # prefix_length - (required) is a type of number
      prefix_length = ip_scope.value["prefix_length"]

      dynamic "static_ip_pool" {
        for_each = ip_scope.value.static_ip_pool
        content {
          # end_address - (required) is a type of string
          end_address = static_ip_pool.value["end_address"]
          # start_address - (required) is a type of string
          start_address = static_ip_pool.value["start_address"]
        }
      }

    }
  }

  dynamic "nsxt_network" {
    for_each = var.nsxt_network
    content {
      # nsxt_manager_id - (required) is a type of string
      nsxt_manager_id = nsxt_network.value["nsxt_manager_id"]
      # nsxt_tier0_router_id - (required) is a type of string
      nsxt_tier0_router_id = nsxt_network.value["nsxt_tier0_router_id"]
    }
  }

  dynamic "vsphere_network" {
    for_each = var.vsphere_network
    content {
      # portgroup_id - (required) is a type of string
      portgroup_id = vsphere_network.value["portgroup_id"]
      # vcenter_id - (required) is a type of string
      vcenter_id = vsphere_network.value["vcenter_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_external_network_v2.this.id
}

output "this" {
  value = vcd_external_network_v2.this
}
```

[top](#index)