# vcd_external_network

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
module "vcd_external_network" {
  source = "./modules/vcd/r/vcd_external_network"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # retain_net_info_across_deployments - (optional) is a type of bool
  retain_net_info_across_deployments = null

  ip_scope = [{
    dns1       = null
    dns2       = null
    dns_suffix = null
    gateway    = null
    netmask    = null
    static_ip_pool = [{
      end_address   = null
      start_address = null
    }]
  }]

  vsphere_network = [{
    name    = null
    type    = null
    vcenter = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "retain_net_info_across_deployments" {
  description = "(optional) - Specifies whether the network resources such as IP/MAC of router will be retained across deployments. Default is false."
  type        = bool
  default     = null
}

variable "ip_scope" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      dns1       = string
      dns2       = string
      dns_suffix = string
      gateway    = string
      netmask    = string
      static_ip_pool = list(object(
        {
          end_address   = string
          start_address = string
        }
      ))
    }
  ))
}

variable "vsphere_network" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      name    = string
      type    = string
      vcenter = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_external_network" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # retain_net_info_across_deployments - (optional) is a type of bool
  retain_net_info_across_deployments = var.retain_net_info_across_deployments

  dynamic "ip_scope" {
    for_each = var.ip_scope
    content {
      # dns1 - (optional) is a type of string
      dns1 = ip_scope.value["dns1"]
      # dns2 - (optional) is a type of string
      dns2 = ip_scope.value["dns2"]
      # dns_suffix - (optional) is a type of string
      dns_suffix = ip_scope.value["dns_suffix"]
      # gateway - (required) is a type of string
      gateway = ip_scope.value["gateway"]
      # netmask - (required) is a type of string
      netmask = ip_scope.value["netmask"]

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

  dynamic "vsphere_network" {
    for_each = var.vsphere_network
    content {
      # name - (required) is a type of string
      name = vsphere_network.value["name"]
      # type - (required) is a type of string
      type = vsphere_network.value["type"]
      # vcenter - (required) is a type of string
      vcenter = vsphere_network.value["vcenter"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_external_network.this.id
}

output "this" {
  value = vcd_external_network.this
}
```

[top](#index)