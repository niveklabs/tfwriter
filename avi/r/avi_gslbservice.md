# avi_gslbservice

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
module "avi_gslbservice" {
  source = "./modules/avi/r/avi_gslbservice"

  # application_persistence_profile_ref - (optional) is a type of string
  application_persistence_profile_ref = null
  # controller_health_status_enabled - (optional) is a type of bool
  controller_health_status_enabled = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # domain_names - (optional) is a type of list of string
  domain_names = []
  # enabled - (optional) is a type of bool
  enabled = null
  # health_monitor_refs - (optional) is a type of list of string
  health_monitor_refs = []
  # health_monitor_scope - (optional) is a type of string
  health_monitor_scope = null
  # hm_off - (optional) is a type of bool
  hm_off = null
  # is_federated - (optional) is a type of bool
  is_federated = null
  # min_members - (optional) is a type of number
  min_members = null
  # name - (required) is a type of string
  name = null
  # num_dns_ip - (optional) is a type of number
  num_dns_ip = null
  # pool_algorithm - (optional) is a type of string
  pool_algorithm = null
  # resolve_cname - (optional) is a type of bool
  resolve_cname = null
  # site_persistence_enabled - (optional) is a type of bool
  site_persistence_enabled = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # ttl - (optional) is a type of number
  ttl = null
  # use_edns_client_subnet - (optional) is a type of bool
  use_edns_client_subnet = null
  # uuid - (optional) is a type of string
  uuid = null
  # wildcard_match - (optional) is a type of bool
  wildcard_match = null

  down_response = [{
    fallback_ip = [{
      addr = null
      type = null
    }]
    fallback_ip6 = [{
      addr = null
      type = null
    }]
    type = null
  }]

  groups = [{
    algorithm             = null
    consistent_hash_mask  = null
    consistent_hash_mask6 = null
    description           = null
    enabled               = null
    fallback_algorithm    = null
    members = [{
      cloud_uuid   = null
      cluster_uuid = null
      description  = null
      enabled      = null
      fqdn         = null
      hostname     = null
      ip = [{
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
      public_ip = [{
        ip = [{
          addr = null
          type = null
        }]
      }]
      ratio              = null
      resolve_fqdn_to_v6 = null
      vs_uuid            = null
    }]
    name     = null
    priority = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "application_persistence_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "controller_health_status_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "health_monitor_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "health_monitor_scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hm_off" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_federated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "min_members" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "num_dns_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pool_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolve_cname" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "site_persistence_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_edns_client_subnet" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wildcard_match" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "down_response" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      fallback_ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      fallback_ip6 = set(object(
        {
          addr = string
          type = string
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      algorithm             = string
      consistent_hash_mask  = number
      consistent_hash_mask6 = number
      description           = string
      enabled               = bool
      fallback_algorithm    = string
      members = list(object(
        {
          cloud_uuid   = string
          cluster_uuid = string
          description  = string
          enabled      = bool
          fqdn         = string
          hostname     = string
          ip = set(object(
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
          public_ip = set(object(
            {
              ip = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
          ratio              = number
          resolve_fqdn_to_v6 = bool
          vs_uuid            = string
        }
      ))
      name     = string
      priority = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_gslbservice" "this" {
  # application_persistence_profile_ref - (optional) is a type of string
  application_persistence_profile_ref = var.application_persistence_profile_ref
  # controller_health_status_enabled - (optional) is a type of bool
  controller_health_status_enabled = var.controller_health_status_enabled
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # domain_names - (optional) is a type of list of string
  domain_names = var.domain_names
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # health_monitor_refs - (optional) is a type of list of string
  health_monitor_refs = var.health_monitor_refs
  # health_monitor_scope - (optional) is a type of string
  health_monitor_scope = var.health_monitor_scope
  # hm_off - (optional) is a type of bool
  hm_off = var.hm_off
  # is_federated - (optional) is a type of bool
  is_federated = var.is_federated
  # min_members - (optional) is a type of number
  min_members = var.min_members
  # name - (required) is a type of string
  name = var.name
  # num_dns_ip - (optional) is a type of number
  num_dns_ip = var.num_dns_ip
  # pool_algorithm - (optional) is a type of string
  pool_algorithm = var.pool_algorithm
  # resolve_cname - (optional) is a type of bool
  resolve_cname = var.resolve_cname
  # site_persistence_enabled - (optional) is a type of bool
  site_persistence_enabled = var.site_persistence_enabled
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # ttl - (optional) is a type of number
  ttl = var.ttl
  # use_edns_client_subnet - (optional) is a type of bool
  use_edns_client_subnet = var.use_edns_client_subnet
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # wildcard_match - (optional) is a type of bool
  wildcard_match = var.wildcard_match

  dynamic "down_response" {
    for_each = var.down_response
    content {
      # type - (optional) is a type of string
      type = down_response.value["type"]

      dynamic "fallback_ip" {
        for_each = down_response.value.fallback_ip
        content {
          # addr - (required) is a type of string
          addr = fallback_ip.value["addr"]
          # type - (required) is a type of string
          type = fallback_ip.value["type"]
        }
      }

      dynamic "fallback_ip6" {
        for_each = down_response.value.fallback_ip6
        content {
          # addr - (required) is a type of string
          addr = fallback_ip6.value["addr"]
          # type - (required) is a type of string
          type = fallback_ip6.value["type"]
        }
      }

    }
  }

  dynamic "groups" {
    for_each = var.groups
    content {
      # algorithm - (optional) is a type of string
      algorithm = groups.value["algorithm"]
      # consistent_hash_mask - (optional) is a type of number
      consistent_hash_mask = groups.value["consistent_hash_mask"]
      # consistent_hash_mask6 - (optional) is a type of number
      consistent_hash_mask6 = groups.value["consistent_hash_mask6"]
      # description - (optional) is a type of string
      description = groups.value["description"]
      # enabled - (optional) is a type of bool
      enabled = groups.value["enabled"]
      # fallback_algorithm - (optional) is a type of string
      fallback_algorithm = groups.value["fallback_algorithm"]
      # name - (optional) is a type of string
      name = groups.value["name"]
      # priority - (optional) is a type of number
      priority = groups.value["priority"]

      dynamic "members" {
        for_each = groups.value.members
        content {
          # cloud_uuid - (optional) is a type of string
          cloud_uuid = members.value["cloud_uuid"]
          # cluster_uuid - (optional) is a type of string
          cluster_uuid = members.value["cluster_uuid"]
          # description - (optional) is a type of string
          description = members.value["description"]
          # enabled - (optional) is a type of bool
          enabled = members.value["enabled"]
          # fqdn - (optional) is a type of string
          fqdn = members.value["fqdn"]
          # hostname - (optional) is a type of string
          hostname = members.value["hostname"]
          # ratio - (optional) is a type of number
          ratio = members.value["ratio"]
          # resolve_fqdn_to_v6 - (optional) is a type of bool
          resolve_fqdn_to_v6 = members.value["resolve_fqdn_to_v6"]
          # vs_uuid - (optional) is a type of string
          vs_uuid = members.value["vs_uuid"]

          dynamic "ip" {
            for_each = members.value.ip
            content {
              # addr - (required) is a type of string
              addr = ip.value["addr"]
              # type - (required) is a type of string
              type = ip.value["type"]
            }
          }

          dynamic "location" {
            for_each = members.value.location
            content {
              # source - (optional) is a type of string
              source = location.value["source"]

              dynamic "location" {
                for_each = location.value.location
                content {
                  # latitude - (optional) is a type of number
                  latitude = location.value["latitude"]
                  # longitude - (optional) is a type of number
                  longitude = location.value["longitude"]
                  # name - (optional) is a type of string
                  name = location.value["name"]
                  # tag - (optional) is a type of string
                  tag = location.value["tag"]
                }
              }

            }
          }

          dynamic "public_ip" {
            for_each = members.value.public_ip
            content {

              dynamic "ip" {
                for_each = public_ip.value.ip
                content {
                  # addr - (required) is a type of string
                  addr = ip.value["addr"]
                  # type - (required) is a type of string
                  type = ip.value["type"]
                }
              }

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
output "application_persistence_profile_ref" {
  description = "returns a string"
  value       = avi_gslbservice.this.application_persistence_profile_ref
}

output "created_by" {
  description = "returns a string"
  value       = avi_gslbservice.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_gslbservice.this.description
}

output "hm_off" {
  description = "returns a bool"
  value       = avi_gslbservice.this.hm_off
}

output "id" {
  description = "returns a string"
  value       = avi_gslbservice.this.id
}

output "num_dns_ip" {
  description = "returns a number"
  value       = avi_gslbservice.this.num_dns_ip
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_gslbservice.this.tenant_ref
}

output "ttl" {
  description = "returns a number"
  value       = avi_gslbservice.this.ttl
}

output "uuid" {
  description = "returns a string"
  value       = avi_gslbservice.this.uuid
}

output "this" {
  value = avi_gslbservice.this
}
```

[top](#index)