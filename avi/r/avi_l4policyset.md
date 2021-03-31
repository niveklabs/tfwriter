# avi_l4policyset

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
module "avi_l4policyset" {
  source = "./modules/avi/r/avi_l4policyset"

  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # is_internal_policy - (optional) is a type of bool
  is_internal_policy = null
  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  l4_connection_policy = [{
    rules = [{
      action = [{
        select_pool = [{
          action_type    = null
          pool_group_ref = null
          pool_ref       = null
        }]
      }]
      enable = null
      index  = null
      match = [{
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
        port = [{
          match_criteria = null
          port_ranges = [{
            end   = null
            start = null
          }]
          ports = []
        }]
        protocol = [{
          match_criteria = null
          protocol       = null
        }]
      }]
      name = null
    }]
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

variable "is_internal_policy" {
  description = "(optional)"
  type        = bool
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

variable "l4_connection_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      rules = list(object(
        {
          action = set(object(
            {
              select_pool = set(object(
                {
                  action_type    = string
                  pool_group_ref = string
                  pool_ref       = string
                }
              ))
            }
          ))
          enable = bool
          index  = number
          match = set(object(
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
              port = set(object(
                {
                  match_criteria = string
                  port_ranges = list(object(
                    {
                      end   = number
                      start = number
                    }
                  ))
                  ports = list(number)
                }
              ))
              protocol = set(object(
                {
                  match_criteria = string
                  protocol       = string
                }
              ))
            }
          ))
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_l4policyset" "this" {
  created_by         = var.created_by
  description        = var.description
  is_internal_policy = var.is_internal_policy
  name               = var.name
  tenant_ref         = var.tenant_ref
  uuid               = var.uuid

  dynamic "l4_connection_policy" {
    for_each = var.l4_connection_policy
    content {

      dynamic "rules" {
        for_each = l4_connection_policy.value.rules
        content {
          enable = rules.value["enable"]
          index  = rules.value["index"]
          name   = rules.value["name"]

          dynamic "action" {
            for_each = rules.value.action
            content {

              dynamic "select_pool" {
                for_each = action.value.select_pool
                content {
                  action_type    = select_pool.value["action_type"]
                  pool_group_ref = select_pool.value["pool_group_ref"]
                  pool_ref       = select_pool.value["pool_ref"]
                }
              }

            }
          }

          dynamic "match" {
            for_each = rules.value.match
            content {

              dynamic "client_ip" {
                for_each = match.value.client_ip
                content {
                  group_refs     = client_ip.value["group_refs"]
                  match_criteria = client_ip.value["match_criteria"]

                  dynamic "addrs" {
                    for_each = client_ip.value.addrs
                    content {
                      addr = addrs.value["addr"]
                      type = addrs.value["type"]
                    }
                  }

                  dynamic "prefixes" {
                    for_each = client_ip.value.prefixes
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
                    for_each = client_ip.value.ranges
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

              dynamic "port" {
                for_each = match.value.port
                content {
                  match_criteria = port.value["match_criteria"]
                  ports          = port.value["ports"]

                  dynamic "port_ranges" {
                    for_each = port.value.port_ranges
                    content {
                      end   = port_ranges.value["end"]
                      start = port_ranges.value["start"]
                    }
                  }

                }
              }

              dynamic "protocol" {
                for_each = match.value.protocol
                content {
                  match_criteria = protocol.value["match_criteria"]
                  protocol       = protocol.value["protocol"]
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
output "created_by" {
  description = "returns a string"
  value       = avi_l4policyset.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_l4policyset.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_l4policyset.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_l4policyset.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_l4policyset.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_l4policyset.this.uuid
}

output "this" {
  value = avi_l4policyset.this
}
```

[top](#index)