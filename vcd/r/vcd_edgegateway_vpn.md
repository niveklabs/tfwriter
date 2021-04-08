# vcd_edgegateway_vpn

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
module "vcd_edgegateway_vpn" {
  source = "./modules/vcd/r/vcd_edgegateway_vpn"

  # description - (optional) is a type of string
  description = null
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # encryption_protocol - (required) is a type of string
  encryption_protocol = null
  # local_id - (required) is a type of string
  local_id = null
  # local_ip_address - (required) is a type of string
  local_ip_address = null
  # mtu - (required) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # peer_id - (required) is a type of string
  peer_id = null
  # peer_ip_address - (required) is a type of string
  peer_ip_address = null
  # shared_secret - (required) is a type of string
  shared_secret = null
  # vdc - (optional) is a type of string
  vdc = null

  local_subnets = [{
    local_subnet_gateway = null
    local_subnet_mask    = null
    local_subnet_name    = null
  }]

  peer_subnets = [{
    peer_subnet_gateway = null
    peer_subnet_mask    = null
    peer_subnet_name    = null
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

variable "edge_gateway" {
  description = "(required)"
  type        = string
}

variable "encryption_protocol" {
  description = "(required)"
  type        = string
}

variable "local_id" {
  description = "(required)"
  type        = string
}

variable "local_ip_address" {
  description = "(required)"
  type        = string
}

variable "mtu" {
  description = "(required)"
  type        = number
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "peer_id" {
  description = "(required)"
  type        = string
}

variable "peer_ip_address" {
  description = "(required)"
  type        = string
}

variable "shared_secret" {
  description = "(required)"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "local_subnets" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      local_subnet_gateway = string
      local_subnet_mask    = string
      local_subnet_name    = string
    }
  ))
  default = []
}

variable "peer_subnets" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      peer_subnet_gateway = string
      peer_subnet_mask    = string
      peer_subnet_name    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_edgegateway_vpn" "this" {
  # description - (optional) is a type of string
  description = var.description
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # encryption_protocol - (required) is a type of string
  encryption_protocol = var.encryption_protocol
  # local_id - (required) is a type of string
  local_id = var.local_id
  # local_ip_address - (required) is a type of string
  local_ip_address = var.local_ip_address
  # mtu - (required) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # peer_id - (required) is a type of string
  peer_id = var.peer_id
  # peer_ip_address - (required) is a type of string
  peer_ip_address = var.peer_ip_address
  # shared_secret - (required) is a type of string
  shared_secret = var.shared_secret
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "local_subnets" {
    for_each = var.local_subnets
    content {
      # local_subnet_gateway - (required) is a type of string
      local_subnet_gateway = local_subnets.value["local_subnet_gateway"]
      # local_subnet_mask - (required) is a type of string
      local_subnet_mask = local_subnets.value["local_subnet_mask"]
      # local_subnet_name - (required) is a type of string
      local_subnet_name = local_subnets.value["local_subnet_name"]
    }
  }

  dynamic "peer_subnets" {
    for_each = var.peer_subnets
    content {
      # peer_subnet_gateway - (required) is a type of string
      peer_subnet_gateway = peer_subnets.value["peer_subnet_gateway"]
      # peer_subnet_mask - (required) is a type of string
      peer_subnet_mask = peer_subnets.value["peer_subnet_mask"]
      # peer_subnet_name - (required) is a type of string
      peer_subnet_name = peer_subnets.value["peer_subnet_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_edgegateway_vpn.this.id
}

output "this" {
  value = vcd_edgegateway_vpn.this
}
```

[top](#index)