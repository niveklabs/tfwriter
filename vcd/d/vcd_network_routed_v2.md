# vcd_network_routed_v2

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
module "vcd_network_routed_v2" {
  source = "./modules/vcd/d/vcd_network_routed_v2"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  filter = [{
    ip         = null
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
      ip         = string
      name_regex = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vcd_network_routed_v2" "this" {
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
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.description
}

output "dns1" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.dns1
}

output "dns2" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.dns2
}

output "dns_suffix" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.dns_suffix
}

output "edge_gateway_id" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.edge_gateway_id
}

output "gateway" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.id
}

output "interface_type" {
  description = "returns a string"
  value       = data.vcd_network_routed_v2.this.interface_type
}

output "prefix_length" {
  description = "returns a number"
  value       = data.vcd_network_routed_v2.this.prefix_length
}

output "static_ip_pool" {
  description = "returns a set of object"
  value       = data.vcd_network_routed_v2.this.static_ip_pool
}

output "this" {
  value = vcd_network_routed_v2.this
}
```

[top](#index)