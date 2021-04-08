# vcd_network_routed

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vcd_network_routed" {
  source = "./modules/vcd/d/vcd_network_routed"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  filter = [{
    ip = null
    metadata = [{
      is_system      = null
      key            = null
      type           = null
      use_api_search = null
      value          = null
    }]
    name_regex = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - A unique name for this network (optional if 'filter' is used)"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip = string
      metadata = list(object(
        {
          is_system      = bool
          key            = string
          type           = string
          use_api_search = bool
          value          = string
        }
      ))
      name_regex = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vcd_network_routed" "this" {
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "filter" {
    for_each = var.filter
    content {
      # ip - (optional) is a type of string
      ip = filter.value["ip"]
      # name_regex - (optional) is a type of string
      name_regex = filter.value["name_regex"]

      dynamic "metadata" {
        for_each = filter.value.metadata
        content {
          # is_system - (optional) is a type of bool
          is_system = metadata.value["is_system"]
          # key - (required) is a type of string
          key = metadata.value["key"]
          # type - (optional) is a type of string
          type = metadata.value["type"]
          # use_api_search - (optional) is a type of bool
          use_api_search = metadata.value["use_api_search"]
          # value - (required) is a type of string
          value = metadata.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.description
}

output "dhcp_pool" {
  description = "returns a set of object"
  value       = data.vcd_network_routed.this.dhcp_pool
}

output "dns1" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.dns1
}

output "dns2" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.dns2
}

output "dns_suffix" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.dns_suffix
}

output "edge_gateway" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.edge_gateway
}

output "gateway" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.gateway
}

output "href" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.href
}

output "id" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.id
}

output "interface_type" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.interface_type
}

output "netmask" {
  description = "returns a string"
  value       = data.vcd_network_routed.this.netmask
}

output "shared" {
  description = "returns a bool"
  value       = data.vcd_network_routed.this.shared
}

output "static_ip_pool" {
  description = "returns a set of object"
  value       = data.vcd_network_routed.this.static_ip_pool
}

output "this" {
  value = vcd_network_routed.this
}
```

[top](#index)