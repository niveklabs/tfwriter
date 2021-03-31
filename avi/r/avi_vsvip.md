# avi_vsvip

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
module "avi_vsvip" {
  source = "./modules/avi/r/avi_vsvip"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # east_west_placement - (optional) is a type of bool
  east_west_placement = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # use_standard_alb - (optional) is a type of bool
  use_standard_alb = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrf_context_ref - (optional) is a type of string
  vrf_context_ref = null
  # vsvip_cloud_config_cksum - (optional) is a type of string
  vsvip_cloud_config_cksum = null

  dns_info = [{
    algorithm = null
    cname = [{
      cname = null
    }]
    fqdn                    = null
    num_records_in_response = null
    ttl                     = null
    type                    = null
  }]

  vip = [{
    auto_allocate_floating_ip = null
    auto_allocate_ip          = null
    auto_allocate_ip_type     = null
    availability_zone         = null
    avi_allocated_fip         = null
    avi_allocated_vip         = null
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
    enabled = null
    floating_ip = [{
      addr = null
      type = null
    }]
    floating_ip6 = [{
      addr = null
      type = null
    }]
    floating_subnet6_uuid = null
    floating_subnet_uuid  = null
    ip6_address = [{
      addr = null
      type = null
    }]
    ip_address = [{
      addr = null
      type = null
    }]
    ipam_network_subnet = [{
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
      subnet6_uuid = null
      subnet_uuid  = null
    }]
    network_ref = null
    placement_networks = [{
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
    port_uuid = null
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
    subnet6_uuid = null
    subnet_uuid  = null
    vip_id       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "east_west_placement" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_standard_alb" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_context_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsvip_cloud_config_cksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      algorithm = string
      cname = set(object(
        {
          cname = string
        }
      ))
      fqdn                    = string
      num_records_in_response = number
      ttl                     = number
      type                    = string
    }
  ))
  default = []
}

variable "vip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_allocate_floating_ip = bool
      auto_allocate_ip          = bool
      auto_allocate_ip_type     = string
      availability_zone         = string
      avi_allocated_fip         = bool
      avi_allocated_vip         = bool
      discovered_networks = list(object(
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
      enabled = bool
      floating_ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      floating_ip6 = set(object(
        {
          addr = string
          type = string
        }
      ))
      floating_subnet6_uuid = string
      floating_subnet_uuid  = string
      ip6_address = set(object(
        {
          addr = string
          type = string
        }
      ))
      ip_address = set(object(
        {
          addr = string
          type = string
        }
      ))
      ipam_network_subnet = set(object(
        {
          network_ref = string
          subnet = set(object(
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
          subnet6 = set(object(
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
          subnet6_uuid = string
          subnet_uuid  = string
        }
      ))
      network_ref = string
      placement_networks = list(object(
        {
          network_ref = string
          subnet = set(object(
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
          subnet6 = set(object(
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
      port_uuid = string
      subnet = set(object(
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
      subnet6 = set(object(
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
      subnet6_uuid = string
      subnet_uuid  = string
      vip_id       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_vsvip" "this" {
  cloud_ref                = var.cloud_ref
  east_west_placement      = var.east_west_placement
  name                     = var.name
  tenant_ref               = var.tenant_ref
  use_standard_alb         = var.use_standard_alb
  uuid                     = var.uuid
  vrf_context_ref          = var.vrf_context_ref
  vsvip_cloud_config_cksum = var.vsvip_cloud_config_cksum

  dynamic "dns_info" {
    for_each = var.dns_info
    content {
      algorithm               = dns_info.value["algorithm"]
      fqdn                    = dns_info.value["fqdn"]
      num_records_in_response = dns_info.value["num_records_in_response"]
      ttl                     = dns_info.value["ttl"]
      type                    = dns_info.value["type"]

      dynamic "cname" {
        for_each = dns_info.value.cname
        content {
          cname = cname.value["cname"]
        }
      }

    }
  }

  dynamic "vip" {
    for_each = var.vip
    content {
      auto_allocate_floating_ip = vip.value["auto_allocate_floating_ip"]
      auto_allocate_ip          = vip.value["auto_allocate_ip"]
      auto_allocate_ip_type     = vip.value["auto_allocate_ip_type"]
      availability_zone         = vip.value["availability_zone"]
      avi_allocated_fip         = vip.value["avi_allocated_fip"]
      avi_allocated_vip         = vip.value["avi_allocated_vip"]
      enabled                   = vip.value["enabled"]
      floating_subnet6_uuid     = vip.value["floating_subnet6_uuid"]
      floating_subnet_uuid      = vip.value["floating_subnet_uuid"]
      network_ref               = vip.value["network_ref"]
      port_uuid                 = vip.value["port_uuid"]
      subnet6_uuid              = vip.value["subnet6_uuid"]
      subnet_uuid               = vip.value["subnet_uuid"]
      vip_id                    = vip.value["vip_id"]

      dynamic "discovered_networks" {
        for_each = vip.value.discovered_networks
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

      dynamic "floating_ip" {
        for_each = vip.value.floating_ip
        content {
          addr = floating_ip.value["addr"]
          type = floating_ip.value["type"]
        }
      }

      dynamic "floating_ip6" {
        for_each = vip.value.floating_ip6
        content {
          addr = floating_ip6.value["addr"]
          type = floating_ip6.value["type"]
        }
      }

      dynamic "ip6_address" {
        for_each = vip.value.ip6_address
        content {
          addr = ip6_address.value["addr"]
          type = ip6_address.value["type"]
        }
      }

      dynamic "ip_address" {
        for_each = vip.value.ip_address
        content {
          addr = ip_address.value["addr"]
          type = ip_address.value["type"]
        }
      }

      dynamic "ipam_network_subnet" {
        for_each = vip.value.ipam_network_subnet
        content {
          network_ref  = ipam_network_subnet.value["network_ref"]
          subnet6_uuid = ipam_network_subnet.value["subnet6_uuid"]
          subnet_uuid  = ipam_network_subnet.value["subnet_uuid"]

          dynamic "subnet" {
            for_each = ipam_network_subnet.value.subnet
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
            for_each = ipam_network_subnet.value.subnet6
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

      dynamic "placement_networks" {
        for_each = vip.value.placement_networks
        content {
          network_ref = placement_networks.value["network_ref"]

          dynamic "subnet" {
            for_each = placement_networks.value.subnet
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
            for_each = placement_networks.value.subnet6
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

      dynamic "subnet" {
        for_each = vip.value.subnet
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
        for_each = vip.value.subnet6
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

}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = avi_vsvip.this.cloud_ref
}

output "id" {
  description = "returns a string"
  value       = avi_vsvip.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_vsvip.this.tenant_ref
}

output "use_standard_alb" {
  description = "returns a bool"
  value       = avi_vsvip.this.use_standard_alb
}

output "uuid" {
  description = "returns a string"
  value       = avi_vsvip.this.uuid
}

output "vrf_context_ref" {
  description = "returns a string"
  value       = avi_vsvip.this.vrf_context_ref
}

output "vsvip_cloud_config_cksum" {
  description = "returns a string"
  value       = avi_vsvip.this.vsvip_cloud_config_cksum
}

output "this" {
  value = avi_vsvip.this
}
```

[top](#index)