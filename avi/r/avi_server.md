# avi_server

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_server" {
  source = "./modules/avi/r/avi_server"

  # autoscaling_group_name - (optional) is a type of string
  autoscaling_group_name = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # description - (optional) is a type of string
  description = null
  # enabled - (optional) is a type of bool
  enabled = null
  # external_orchestration_id - (optional) is a type of string
  external_orchestration_id = null
  # external_uuid - (optional) is a type of string
  external_uuid = null
  # hostname - (optional) is a type of string
  hostname = null
  # ip - (required) is a type of string
  ip = null
  # mac_address - (optional) is a type of string
  mac_address = null
  # nw_ref - (optional) is a type of string
  nw_ref = null
  # pool_ref - (required) is a type of string
  pool_ref = null
  # port - (optional) is a type of number
  port = null
  # prst_hdr_val - (optional) is a type of string
  prst_hdr_val = null
  # ratio - (optional) is a type of number
  ratio = null
  # resolve_server_by_dns - (optional) is a type of bool
  resolve_server_by_dns = null
  # rewrite_host_header - (optional) is a type of bool
  rewrite_host_header = null
  # server_node - (optional) is a type of string
  server_node = null
  # static - (optional) is a type of bool
  static = null
  # type - (optional) is a type of string
  type = null
  # verify_network - (optional) is a type of bool
  verify_network = null
  # vm_ref - (optional) is a type of string
  vm_ref = null

  discovered_networks = [{
    network_ref = null
    subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    subnet6 = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
  }]

  location = [{
    latitude  = null
    longitude = null
    name      = null
    tag       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "autoscaling_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "external_orchestration_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "mac_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nw_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_ref" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "prst_hdr_val" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ratio" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resolve_server_by_dns" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "rewrite_host_header" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "server_node" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "static" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "verify_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vm_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "discovered_networks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      network_ref = string
      subnet = list(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      subnet6 = list(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
    }
  ))
  default = []
}

variable "location" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      latitude  = number
      longitude = number
      name      = string
      tag       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_server" "this" {
  autoscaling_group_name    = var.autoscaling_group_name
  availability_zone         = var.availability_zone
  description               = var.description
  enabled                   = var.enabled
  external_orchestration_id = var.external_orchestration_id
  external_uuid             = var.external_uuid
  hostname                  = var.hostname
  ip                        = var.ip
  mac_address               = var.mac_address
  nw_ref                    = var.nw_ref
  pool_ref                  = var.pool_ref
  port                      = var.port
  prst_hdr_val              = var.prst_hdr_val
  ratio                     = var.ratio
  resolve_server_by_dns     = var.resolve_server_by_dns
  rewrite_host_header       = var.rewrite_host_header
  server_node               = var.server_node
  static                    = var.static
  type                      = var.type
  verify_network            = var.verify_network
  vm_ref                    = var.vm_ref

  dynamic "discovered_networks" {
    for_each = var.discovered_networks
    content {
      network_ref = discovered_networks.value["network_ref"]

      dynamic "subnet" {
        for_each = discovered_networks.value.subnet
        content {
          mask = subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "subnet6" {
        for_each = discovered_networks.value.subnet6
        content {
          mask = subnet6.value["mask"]

          dynamic "ip_addr" {
            for_each = subnet6.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "location" {
    for_each = var.location
    content {
      latitude  = location.value["latitude"]
      longitude = location.value["longitude"]
      name      = location.value["name"]
      tag       = location.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_server.this.id
}

output "nw_ref" {
  description = "returns a string"
  value       = avi_server.this.nw_ref
}

output "vm_ref" {
  description = "returns a string"
  value       = avi_server.this.vm_ref
}

output "this" {
  value = avi_server.this
}
```

[top](#index)