# thunder_rib_route

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_rib_route" {
  source = "./modules/thunder/r/thunder_rib_route"

  # ip_dest_addr - (optional) is a type of string
  ip_dest_addr = null
  # ip_mask - (optional) is a type of string
  ip_mask = null
  # uuid - (optional) is a type of string
  uuid = null

  ip_nexthop_ipv4 = [{
    description_nexthop_ip = null
    distance_nexthop_ip    = null
    ip_next_hop            = null
  }]

  ip_nexthop_lif = [{
    description_nexthop_lif = null
    lif                     = null
  }]

  ip_nexthop_partition = [{
    description_nexthop_partition = null
    description_partition_vrid    = null
    partition_name                = null
    vrid_num_in_partition         = null
  }]

  ip_nexthop_tunnel = [{
    description_nexthop_tunnel = null
    distance_nexthop_tunnel    = null
    ip_next_hop_tunnel         = null
    tunnel                     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ip_dest_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_mask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_nexthop_ipv4" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description_nexthop_ip = string
      distance_nexthop_ip    = number
      ip_next_hop            = string
    }
  ))
  default = []
}

variable "ip_nexthop_lif" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description_nexthop_lif = string
      lif                     = number
    }
  ))
  default = []
}

variable "ip_nexthop_partition" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description_nexthop_partition = string
      description_partition_vrid    = string
      partition_name                = string
      vrid_num_in_partition         = number
    }
  ))
  default = []
}

variable "ip_nexthop_tunnel" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description_nexthop_tunnel = string
      distance_nexthop_tunnel    = number
      ip_next_hop_tunnel         = string
      tunnel                     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_rib_route" "this" {
  ip_dest_addr = var.ip_dest_addr
  ip_mask      = var.ip_mask
  uuid         = var.uuid

  dynamic "ip_nexthop_ipv4" {
    for_each = var.ip_nexthop_ipv4
    content {
      description_nexthop_ip = ip_nexthop_ipv4.value["description_nexthop_ip"]
      distance_nexthop_ip    = ip_nexthop_ipv4.value["distance_nexthop_ip"]
      ip_next_hop            = ip_nexthop_ipv4.value["ip_next_hop"]
    }
  }

  dynamic "ip_nexthop_lif" {
    for_each = var.ip_nexthop_lif
    content {
      description_nexthop_lif = ip_nexthop_lif.value["description_nexthop_lif"]
      lif                     = ip_nexthop_lif.value["lif"]
    }
  }

  dynamic "ip_nexthop_partition" {
    for_each = var.ip_nexthop_partition
    content {
      description_nexthop_partition = ip_nexthop_partition.value["description_nexthop_partition"]
      description_partition_vrid    = ip_nexthop_partition.value["description_partition_vrid"]
      partition_name                = ip_nexthop_partition.value["partition_name"]
      vrid_num_in_partition         = ip_nexthop_partition.value["vrid_num_in_partition"]
    }
  }

  dynamic "ip_nexthop_tunnel" {
    for_each = var.ip_nexthop_tunnel
    content {
      description_nexthop_tunnel = ip_nexthop_tunnel.value["description_nexthop_tunnel"]
      distance_nexthop_tunnel    = ip_nexthop_tunnel.value["distance_nexthop_tunnel"]
      ip_next_hop_tunnel         = ip_nexthop_tunnel.value["ip_next_hop_tunnel"]
      tunnel                     = ip_nexthop_tunnel.value["tunnel"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_rib_route.this.id
}

output "this" {
  value = thunder_rib_route.this
}
```

[top](#index)