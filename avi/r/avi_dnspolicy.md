# avi_dnspolicy

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
module "avi_dnspolicy" {
  source = "./modules/avi/r/avi_dnspolicy"

  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  rule = [{
    action = [{
      allow = [{
        allow      = null
        reset_conn = null
      }]
      dns_rate_limiter = [{
        action = [{
          type = null
        }]
        rate_limiter_object = [{
          burst_sz = null
          count    = null
          name     = null
          period   = null
        }]
      }]
      gslb_site_selection = [{
        fallback_site_names = []
        is_site_preferred   = null
        site_name           = null
      }]
      pool_switching = [{
        pool_group_ref = null
        pool_ref       = null
      }]
      response = [{
        authoritative = null
        rcode         = null
        resource_record_sets = [{
          resource_record_set = [{
            cname = [{
              cname = null
            }]
            fqdn = null
            ip6_addresses = [{
              ip6_address = [{
                addr = null
                type = null
              }]
            }]
            ip_addresses = [{
              ip_address = [{
                addr = null
                type = null
              }]
            }]
            nses = [{
              ip6_address = [{
                addr = null
                type = null
              }]
              ip_address = [{
                addr = null
                type = null
              }]
              nsname = null
            }]
            ttl  = null
            type = null
          }]
          section = null
        }]
        truncation = null
      }]
    }]
    enable = null
    index  = null
    log    = null
    match = [{
      client_ip_address = [{
        client_ip = [{
          addrs = [{
            addr = null
            type = null
          }]
          group_refs     = []
          match_criteria = null
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
        }]
        use_edns_client_subnet_ip = null
      }]
      geo_location = [{
        geolocation_name          = null
        geolocation_tag           = null
        match_criteria            = null
        use_edns_client_subnet_ip = null
      }]
      protocol = [{
        match_criteria = null
        protocol       = null
      }]
      query_name = [{
        match_criteria     = null
        query_domain_names = []
        string_group_refs  = []
      }]
      query_type = [{
        match_criteria = null
        query_type     = []
      }]
    }]
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "name" {
  description = "(optional)"
  type        = string
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

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = set(object(
        {
          allow = set(object(
            {
              allow      = bool
              reset_conn = bool
            }
          ))
          dns_rate_limiter = set(object(
            {
              action = set(object(
                {
                  type = string
                }
              ))
              rate_limiter_object = set(object(
                {
                  burst_sz = number
                  count    = number
                  name     = string
                  period   = number
                }
              ))
            }
          ))
          gslb_site_selection = set(object(
            {
              fallback_site_names = list(string)
              is_site_preferred   = bool
              site_name           = string
            }
          ))
          pool_switching = set(object(
            {
              pool_group_ref = string
              pool_ref       = string
            }
          ))
          response = set(object(
            {
              authoritative = bool
              rcode         = string
              resource_record_sets = list(object(
                {
                  resource_record_set = set(object(
                    {
                      cname = set(object(
                        {
                          cname = string
                        }
                      ))
                      fqdn = string
                      ip6_addresses = list(object(
                        {
                          ip6_address = set(object(
                            {
                              addr = string
                              type = string
                            }
                          ))
                        }
                      ))
                      ip_addresses = list(object(
                        {
                          ip_address = set(object(
                            {
                              addr = string
                              type = string
                            }
                          ))
                        }
                      ))
                      nses = list(object(
                        {
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
                          nsname = string
                        }
                      ))
                      ttl  = number
                      type = string
                    }
                  ))
                  section = string
                }
              ))
              truncation = bool
            }
          ))
        }
      ))
      enable = bool
      index  = number
      log    = bool
      match = set(object(
        {
          client_ip_address = set(object(
            {
              client_ip = set(object(
                {
                  addrs = list(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  group_refs     = list(string)
                  match_criteria = string
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
                }
              ))
              use_edns_client_subnet_ip = bool
            }
          ))
          geo_location = set(object(
            {
              geolocation_name          = string
              geolocation_tag           = string
              match_criteria            = string
              use_edns_client_subnet_ip = bool
            }
          ))
          protocol = set(object(
            {
              match_criteria = string
              protocol       = string
            }
          ))
          query_name = set(object(
            {
              match_criteria     = string
              query_domain_names = list(string)
              string_group_refs  = list(string)
            }
          ))
          query_type = set(object(
            {
              match_criteria = string
              query_type     = list(string)
            }
          ))
        }
      ))
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_dnspolicy" "this" {
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "rule" {
    for_each = var.rule
    content {
      # enable - (optional) is a type of bool
      enable = rule.value["enable"]
      # index - (optional) is a type of number
      index = rule.value["index"]
      # log - (optional) is a type of bool
      log = rule.value["log"]
      # name - (optional) is a type of string
      name = rule.value["name"]

      dynamic "action" {
        for_each = rule.value.action
        content {

          dynamic "allow" {
            for_each = action.value.allow
            content {
              # allow - (optional) is a type of bool
              allow = allow.value["allow"]
              # reset_conn - (optional) is a type of bool
              reset_conn = allow.value["reset_conn"]
            }
          }

          dynamic "dns_rate_limiter" {
            for_each = action.value.dns_rate_limiter
            content {

              dynamic "action" {
                for_each = dns_rate_limiter.value.action
                content {
                  # type - (optional) is a type of string
                  type = action.value["type"]
                }
              }

              dynamic "rate_limiter_object" {
                for_each = dns_rate_limiter.value.rate_limiter_object
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter_object.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter_object.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter_object.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter_object.value["period"]
                }
              }

            }
          }

          dynamic "gslb_site_selection" {
            for_each = action.value.gslb_site_selection
            content {
              # fallback_site_names - (optional) is a type of list of string
              fallback_site_names = gslb_site_selection.value["fallback_site_names"]
              # is_site_preferred - (optional) is a type of bool
              is_site_preferred = gslb_site_selection.value["is_site_preferred"]
              # site_name - (optional) is a type of string
              site_name = gslb_site_selection.value["site_name"]
            }
          }

          dynamic "pool_switching" {
            for_each = action.value.pool_switching
            content {
              # pool_group_ref - (optional) is a type of string
              pool_group_ref = pool_switching.value["pool_group_ref"]
              # pool_ref - (optional) is a type of string
              pool_ref = pool_switching.value["pool_ref"]
            }
          }

          dynamic "response" {
            for_each = action.value.response
            content {
              # authoritative - (optional) is a type of bool
              authoritative = response.value["authoritative"]
              # rcode - (optional) is a type of string
              rcode = response.value["rcode"]
              # truncation - (optional) is a type of bool
              truncation = response.value["truncation"]

              dynamic "resource_record_sets" {
                for_each = response.value.resource_record_sets
                content {
                  # section - (optional) is a type of string
                  section = resource_record_sets.value["section"]

                  dynamic "resource_record_set" {
                    for_each = resource_record_sets.value.resource_record_set
                    content {
                      # fqdn - (optional) is a type of string
                      fqdn = resource_record_set.value["fqdn"]
                      # ttl - (optional) is a type of number
                      ttl = resource_record_set.value["ttl"]
                      # type - (optional) is a type of string
                      type = resource_record_set.value["type"]

                      dynamic "cname" {
                        for_each = resource_record_set.value.cname
                        content {
                          # cname - (required) is a type of string
                          cname = cname.value["cname"]
                        }
                      }

                      dynamic "ip6_addresses" {
                        for_each = resource_record_set.value.ip6_addresses
                        content {

                          dynamic "ip6_address" {
                            for_each = ip6_addresses.value.ip6_address
                            content {
                              # addr - (required) is a type of string
                              addr = ip6_address.value["addr"]
                              # type - (required) is a type of string
                              type = ip6_address.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "ip_addresses" {
                        for_each = resource_record_set.value.ip_addresses
                        content {

                          dynamic "ip_address" {
                            for_each = ip_addresses.value.ip_address
                            content {
                              # addr - (required) is a type of string
                              addr = ip_address.value["addr"]
                              # type - (required) is a type of string
                              type = ip_address.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "nses" {
                        for_each = resource_record_set.value.nses
                        content {
                          # nsname - (required) is a type of string
                          nsname = nses.value["nsname"]

                          dynamic "ip6_address" {
                            for_each = nses.value.ip6_address
                            content {
                              # addr - (required) is a type of string
                              addr = ip6_address.value["addr"]
                              # type - (required) is a type of string
                              type = ip6_address.value["type"]
                            }
                          }

                          dynamic "ip_address" {
                            for_each = nses.value.ip_address
                            content {
                              # addr - (required) is a type of string
                              addr = ip_address.value["addr"]
                              # type - (required) is a type of string
                              type = ip_address.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "match" {
        for_each = rule.value.match
        content {

          dynamic "client_ip_address" {
            for_each = match.value.client_ip_address
            content {
              # use_edns_client_subnet_ip - (optional) is a type of bool
              use_edns_client_subnet_ip = client_ip_address.value["use_edns_client_subnet_ip"]

              dynamic "client_ip" {
                for_each = client_ip_address.value.client_ip
                content {
                  # group_refs - (optional) is a type of list of string
                  group_refs = client_ip.value["group_refs"]
                  # match_criteria - (required) is a type of string
                  match_criteria = client_ip.value["match_criteria"]

                  dynamic "addrs" {
                    for_each = client_ip.value.addrs
                    content {
                      # addr - (required) is a type of string
                      addr = addrs.value["addr"]
                      # type - (required) is a type of string
                      type = addrs.value["type"]
                    }
                  }

                  dynamic "prefixes" {
                    for_each = client_ip.value.prefixes
                    content {
                      # mask - (required) is a type of number
                      mask = prefixes.value["mask"]

                      dynamic "ip_addr" {
                        for_each = prefixes.value.ip_addr
                        content {
                          # addr - (required) is a type of string
                          addr = ip_addr.value["addr"]
                          # type - (required) is a type of string
                          type = ip_addr.value["type"]
                        }
                      }

                    }
                  }

                  dynamic "ranges" {
                    for_each = client_ip.value.ranges
                    content {

                      dynamic "begin" {
                        for_each = ranges.value.begin
                        content {
                          # addr - (required) is a type of string
                          addr = begin.value["addr"]
                          # type - (required) is a type of string
                          type = begin.value["type"]
                        }
                      }

                      dynamic "end" {
                        for_each = ranges.value.end
                        content {
                          # addr - (required) is a type of string
                          addr = end.value["addr"]
                          # type - (required) is a type of string
                          type = end.value["type"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "geo_location" {
            for_each = match.value.geo_location
            content {
              # geolocation_name - (optional) is a type of string
              geolocation_name = geo_location.value["geolocation_name"]
              # geolocation_tag - (optional) is a type of string
              geolocation_tag = geo_location.value["geolocation_tag"]
              # match_criteria - (optional) is a type of string
              match_criteria = geo_location.value["match_criteria"]
              # use_edns_client_subnet_ip - (optional) is a type of bool
              use_edns_client_subnet_ip = geo_location.value["use_edns_client_subnet_ip"]
            }
          }

          dynamic "protocol" {
            for_each = match.value.protocol
            content {
              # match_criteria - (optional) is a type of string
              match_criteria = protocol.value["match_criteria"]
              # protocol - (optional) is a type of string
              protocol = protocol.value["protocol"]
            }
          }

          dynamic "query_name" {
            for_each = match.value.query_name
            content {
              # match_criteria - (optional) is a type of string
              match_criteria = query_name.value["match_criteria"]
              # query_domain_names - (optional) is a type of list of string
              query_domain_names = query_name.value["query_domain_names"]
              # string_group_refs - (optional) is a type of list of string
              string_group_refs = query_name.value["string_group_refs"]
            }
          }

          dynamic "query_type" {
            for_each = match.value.query_type
            content {
              # match_criteria - (optional) is a type of string
              match_criteria = query_type.value["match_criteria"]
              # query_type - (optional) is a type of list of string
              query_type = query_type.value["query_type"]
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
output "created_by" {
  description = "returns a string"
  value       = avi_dnspolicy.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_dnspolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_dnspolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_dnspolicy.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_dnspolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_dnspolicy.this.uuid
}

output "this" {
  value = avi_dnspolicy.this
}
```

[top](#index)