# avi_natpolicy

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
module "avi_natpolicy" {
  source = "./modules/avi/r/avi_natpolicy"

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

  rules = [{
    action = [{
      nat_info = [{
        nat_ip = [{
          addr = null
          type = null
        }]
        nat_ip_range = [{
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
      type = null
    }]
    created_by = null
    enable     = null
    index      = null
    match = [{
      destination_ip = [{
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
      services = [{
        destination_port = [{
          match_criteria = null
          ports          = []
        }]
        source_port = [{
          match_criteria = null
          ports          = []
        }]
      }]
      source_ip = [{
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

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = set(object(
        {
          nat_info = list(object(
            {
              nat_ip = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              nat_ip_range = set(object(
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
          type = string
        }
      ))
      created_by = string
      enable     = bool
      index      = number
      match = set(object(
        {
          destination_ip = set(object(
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
          services = set(object(
            {
              destination_port = set(object(
                {
                  match_criteria = string
                  ports          = list(number)
                }
              ))
              source_port = set(object(
                {
                  match_criteria = string
                  ports          = list(number)
                }
              ))
            }
          ))
          source_ip = set(object(
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
resource "avi_natpolicy" "this" {
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

  dynamic "rules" {
    for_each = var.rules
    content {
      # created_by - (optional) is a type of string
      created_by = rules.value["created_by"]
      # enable - (optional) is a type of bool
      enable = rules.value["enable"]
      # index - (optional) is a type of number
      index = rules.value["index"]
      # name - (optional) is a type of string
      name = rules.value["name"]

      dynamic "action" {
        for_each = rules.value.action
        content {
          # type - (optional) is a type of string
          type = action.value["type"]

          dynamic "nat_info" {
            for_each = action.value.nat_info
            content {

              dynamic "nat_ip" {
                for_each = nat_info.value.nat_ip
                content {
                  # addr - (required) is a type of string
                  addr = nat_ip.value["addr"]
                  # type - (required) is a type of string
                  type = nat_ip.value["type"]
                }
              }

              dynamic "nat_ip_range" {
                for_each = nat_info.value.nat_ip_range
                content {

                  dynamic "begin" {
                    for_each = nat_ip_range.value.begin
                    content {
                      # addr - (required) is a type of string
                      addr = begin.value["addr"]
                      # type - (required) is a type of string
                      type = begin.value["type"]
                    }
                  }

                  dynamic "end" {
                    for_each = nat_ip_range.value.end
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

      dynamic "match" {
        for_each = rules.value.match
        content {

          dynamic "destination_ip" {
            for_each = match.value.destination_ip
            content {
              # group_refs - (optional) is a type of list of string
              group_refs = destination_ip.value["group_refs"]
              # match_criteria - (required) is a type of string
              match_criteria = destination_ip.value["match_criteria"]

              dynamic "addrs" {
                for_each = destination_ip.value.addrs
                content {
                  # addr - (required) is a type of string
                  addr = addrs.value["addr"]
                  # type - (required) is a type of string
                  type = addrs.value["type"]
                }
              }

              dynamic "prefixes" {
                for_each = destination_ip.value.prefixes
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
                for_each = destination_ip.value.ranges
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

          dynamic "services" {
            for_each = match.value.services
            content {

              dynamic "destination_port" {
                for_each = services.value.destination_port
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = destination_port.value["match_criteria"]
                  # ports - (optional) is a type of list of number
                  ports = destination_port.value["ports"]
                }
              }

              dynamic "source_port" {
                for_each = services.value.source_port
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = source_port.value["match_criteria"]
                  # ports - (optional) is a type of list of number
                  ports = source_port.value["ports"]
                }
              }

            }
          }

          dynamic "source_ip" {
            for_each = match.value.source_ip
            content {
              # group_refs - (optional) is a type of list of string
              group_refs = source_ip.value["group_refs"]
              # match_criteria - (required) is a type of string
              match_criteria = source_ip.value["match_criteria"]

              dynamic "addrs" {
                for_each = source_ip.value.addrs
                content {
                  # addr - (required) is a type of string
                  addr = addrs.value["addr"]
                  # type - (required) is a type of string
                  type = addrs.value["type"]
                }
              }

              dynamic "prefixes" {
                for_each = source_ip.value.prefixes
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
                for_each = source_ip.value.ranges
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

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = avi_natpolicy.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_natpolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_natpolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_natpolicy.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_natpolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_natpolicy.this.uuid
}

output "this" {
  value = avi_natpolicy.this
}
```

[top](#index)