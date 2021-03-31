# avi_gslb

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
module "avi_gslb" {
  source = "./modules/avi/r/avi_gslb"

  # async_interval - (optional) is a type of number
  async_interval = null
  # clear_on_max_retries - (optional) is a type of number
  clear_on_max_retries = null
  # description - (optional) is a type of string
  description = null
  # error_resync_interval - (optional) is a type of number
  error_resync_interval = null
  # is_federated - (optional) is a type of bool
  is_federated = null
  # leader_cluster_uuid - (optional) is a type of string
  leader_cluster_uuid = null
  # maintenance_mode - (optional) is a type of bool
  maintenance_mode = null
  # name - (required) is a type of string
  name = null
  # send_interval - (optional) is a type of number
  send_interval = null
  # send_interval_prior_to_maintenance_mode - (optional) is a type of number
  send_interval_prior_to_maintenance_mode = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # view_id - (optional) is a type of number
  view_id = null

  client_ip_addr_group = [{
    addrs = [{
      addr = null
      type = null
    }]
    prefixes = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    ranges = [{
      begin = [{
        addr = null
        type = null
      }]
      end = [{
        addr = null
        type = null
      }]
    }]
    type = null
  }]

  dns_configs = [{
    domain_name = null
  }]

  sites = [{
    address      = null
    cluster_uuid = null
    dns_vses = [{
      dns_vs_uuid  = null
      domain_names = []
    }]
    enabled = null
    hm_proxies = [{
      proxy_type = null
      site_uuid  = null
    }]
    hm_shard_enabled = null
    ip_addresses = [{
      addr = null
      type = null
    }]
    location = [{
      location = [{
        latitude  = null
        longitude = null
        name      = null
        tag       = null
      }]
      source = null
    }]
    member_type = null
    name        = null
    password    = null
    port        = null
    ratio       = null
    username    = null
    uuid        = null
  }]

  third_party_sites = [{
    enabled = null
    hm_proxies = [{
      proxy_type = null
      site_uuid  = null
    }]
    location = [{
      location = [{
        latitude  = null
        longitude = null
        name      = null
        tag       = null
      }]
      source = null
    }]
    name  = null
    ratio = null
    uuid  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "async_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "clear_on_max_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "error_resync_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "is_federated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "leader_cluster_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintenance_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "send_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "send_interval_prior_to_maintenance_mode" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "view_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "client_ip_addr_group" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      addrs = list(object(
        {
          addr = string
          type = string
        }
      ))
      prefixes = list(object(
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
      ranges = list(object(
        {
          begin = set(object(
            {
              addr = string
              type = string
            }
          ))
          end = set(object(
            {
              addr = string
              type = string
            }
          ))
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "dns_configs" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      domain_name = string
    }
  ))
  default = []
}

variable "sites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      address      = string
      cluster_uuid = string
      dns_vses = list(object(
        {
          dns_vs_uuid  = string
          domain_names = list(string)
        }
      ))
      enabled = bool
      hm_proxies = list(object(
        {
          proxy_type = string
          site_uuid  = string
        }
      ))
      hm_shard_enabled = bool
      ip_addresses = list(object(
        {
          addr = string
          type = string
        }
      ))
      location = set(object(
        {
          location = set(object(
            {
              latitude  = number
              longitude = number
              name      = string
              tag       = string
            }
          ))
          source = string
        }
      ))
      member_type = string
      name        = string
      password    = string
      port        = number
      ratio       = number
      username    = string
      uuid        = string
    }
  ))
  default = []
}

variable "third_party_sites" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enabled = bool
      hm_proxies = list(object(
        {
          proxy_type = string
          site_uuid  = string
        }
      ))
      location = set(object(
        {
          location = set(object(
            {
              latitude  = number
              longitude = number
              name      = string
              tag       = string
            }
          ))
          source = string
        }
      ))
      name  = string
      ratio = number
      uuid  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_gslb" "this" {
  async_interval                          = var.async_interval
  clear_on_max_retries                    = var.clear_on_max_retries
  description                             = var.description
  error_resync_interval                   = var.error_resync_interval
  is_federated                            = var.is_federated
  leader_cluster_uuid                     = var.leader_cluster_uuid
  maintenance_mode                        = var.maintenance_mode
  name                                    = var.name
  send_interval                           = var.send_interval
  send_interval_prior_to_maintenance_mode = var.send_interval_prior_to_maintenance_mode
  tenant_ref                              = var.tenant_ref
  uuid                                    = var.uuid
  view_id                                 = var.view_id

  dynamic "client_ip_addr_group" {
    for_each = var.client_ip_addr_group
    content {
      type = client_ip_addr_group.value["type"]

      dynamic "addrs" {
        for_each = client_ip_addr_group.value.addrs
        content {
          addr = addrs.value["addr"]
          type = addrs.value["type"]
        }
      }

      dynamic "prefixes" {
        for_each = client_ip_addr_group.value.prefixes
        content {
          mask = prefixes.value["mask"]

          dynamic "ip_addr" {
            for_each = prefixes.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "ranges" {
        for_each = client_ip_addr_group.value.ranges
        content {

          dynamic "begin" {
            for_each = ranges.value.begin
            content {
              addr = begin.value["addr"]
              type = begin.value["type"]
            }
          }

          dynamic "end" {
            for_each = ranges.value.end
            content {
              addr = end.value["addr"]
              type = end.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "dns_configs" {
    for_each = var.dns_configs
    content {
      domain_name = dns_configs.value["domain_name"]
    }
  }

  dynamic "sites" {
    for_each = var.sites
    content {
      address          = sites.value["address"]
      cluster_uuid     = sites.value["cluster_uuid"]
      enabled          = sites.value["enabled"]
      hm_shard_enabled = sites.value["hm_shard_enabled"]
      member_type      = sites.value["member_type"]
      name             = sites.value["name"]
      password         = sites.value["password"]
      port             = sites.value["port"]
      ratio            = sites.value["ratio"]
      username         = sites.value["username"]
      uuid             = sites.value["uuid"]

      dynamic "dns_vses" {
        for_each = sites.value.dns_vses
        content {
          dns_vs_uuid  = dns_vses.value["dns_vs_uuid"]
          domain_names = dns_vses.value["domain_names"]
        }
      }

      dynamic "hm_proxies" {
        for_each = sites.value.hm_proxies
        content {
          proxy_type = hm_proxies.value["proxy_type"]
          site_uuid  = hm_proxies.value["site_uuid"]
        }
      }

      dynamic "ip_addresses" {
        for_each = sites.value.ip_addresses
        content {
          addr = ip_addresses.value["addr"]
          type = ip_addresses.value["type"]
        }
      }

      dynamic "location" {
        for_each = sites.value.location
        content {
          source = location.value["source"]

          dynamic "location" {
            for_each = location.value.location
            content {
              latitude  = location.value["latitude"]
              longitude = location.value["longitude"]
              name      = location.value["name"]
              tag       = location.value["tag"]
            }
          }

        }
      }

    }
  }

  dynamic "third_party_sites" {
    for_each = var.third_party_sites
    content {
      enabled = third_party_sites.value["enabled"]
      name    = third_party_sites.value["name"]
      ratio   = third_party_sites.value["ratio"]
      uuid    = third_party_sites.value["uuid"]

      dynamic "hm_proxies" {
        for_each = third_party_sites.value.hm_proxies
        content {
          proxy_type = hm_proxies.value["proxy_type"]
          site_uuid  = hm_proxies.value["site_uuid"]
        }
      }

      dynamic "location" {
        for_each = third_party_sites.value.location
        content {
          source = location.value["source"]

          dynamic "location" {
            for_each = location.value.location
            content {
              latitude  = location.value["latitude"]
              longitude = location.value["longitude"]
              name      = location.value["name"]
              tag       = location.value["tag"]
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
output "description" {
  description = "returns a string"
  value       = avi_gslb.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_gslb.this.id
}

output "leader_cluster_uuid" {
  description = "returns a string"
  value       = avi_gslb.this.leader_cluster_uuid
}

output "send_interval_prior_to_maintenance_mode" {
  description = "returns a number"
  value       = avi_gslb.this.send_interval_prior_to_maintenance_mode
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_gslb.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_gslb.this.uuid
}

output "this" {
  value = avi_gslb.this
}
```

[top](#index)