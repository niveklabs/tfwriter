# avi_networksecuritypolicy

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
module "avi_networksecuritypolicy" {
  source = "./modules/avi/r/avi_networksecuritypolicy"

  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = null
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
    action     = null
    age        = null
    created_by = null
    enable     = null
    index      = null
    log        = null
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
      microservice = [{
        group_ref      = null
        match_criteria = null
      }]
      vs_port = [{
        match_criteria = null
        ports          = []
      }]
    }]
    name = null
    rl_param = [{
      burst_size = null
      max_rate   = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_config_cksum" {
  description = "(optional)"
  type        = string
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
      action     = string
      age        = number
      created_by = string
      enable     = bool
      index      = number
      log        = bool
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
          microservice = set(object(
            {
              group_ref      = string
              match_criteria = string
            }
          ))
          vs_port = set(object(
            {
              match_criteria = string
              ports          = list(number)
            }
          ))
        }
      ))
      name = string
      rl_param = set(object(
        {
          burst_size = number
          max_rate   = number
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
resource "avi_networksecuritypolicy" "this" {
  cloud_config_cksum = var.cloud_config_cksum
  created_by         = var.created_by
  description        = var.description
  name               = var.name
  tenant_ref         = var.tenant_ref
  uuid               = var.uuid

  dynamic "rules" {
    for_each = var.rules
    content {
      action     = rules.value["action"]
      age        = rules.value["age"]
      created_by = rules.value["created_by"]
      enable     = rules.value["enable"]
      index      = rules.value["index"]
      log        = rules.value["log"]
      name       = rules.value["name"]

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

          dynamic "microservice" {
            for_each = match.value.microservice
            content {
              group_ref      = microservice.value["group_ref"]
              match_criteria = microservice.value["match_criteria"]
            }
          }

          dynamic "vs_port" {
            for_each = match.value.vs_port
            content {
              match_criteria = vs_port.value["match_criteria"]
              ports          = vs_port.value["ports"]
            }
          }

        }
      }

      dynamic "rl_param" {
        for_each = rules.value.rl_param
        content {
          burst_size = rl_param.value["burst_size"]
          max_rate   = rl_param.value["max_rate"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_config_cksum" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.cloud_config_cksum
}

output "created_by" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_networksecuritypolicy.this.uuid
}

output "this" {
  value = avi_networksecuritypolicy.this
}
```

[top](#index)