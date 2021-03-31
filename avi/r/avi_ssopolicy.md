# avi_ssopolicy

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
module "avi_ssopolicy" {
  source = "./modules/avi/r/avi_ssopolicy"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (optional) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  authentication_policy = [{
    authn_rules = [{
      action = [{
        type = null
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
        host_hdr = [{
          match_case     = null
          match_criteria = null
          value          = []
        }]
        path = [{
          match_case        = null
          match_criteria    = null
          match_str         = []
          string_group_refs = []
        }]
      }]
      name = null
    }]
    default_auth_profile_ref = null
  }]

  authorization_policy = [{
    authz_rules = [{
      action = [{
        status_code = null
        type        = null
      }]
      enable = null
      index  = null
      match = [{
        attr_matches = [{
          attribute_name = null
          attribute_value_list = [{
            match_criteria    = null
            match_str         = []
            string_group_refs = []
          }]
        }]
        host_hdr = [{
          match_case     = null
          match_criteria = null
          value          = []
        }]
        method = [{
          match_criteria = null
          methods        = []
        }]
        path = [{
          match_case        = null
          match_criteria    = null
          match_str         = []
          string_group_refs = []
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authentication_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      authn_rules = list(object(
        {
          action = set(object(
            {
              type = string
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
              host_hdr = set(object(
                {
                  match_case     = string
                  match_criteria = string
                  value          = list(string)
                }
              ))
              path = set(object(
                {
                  match_case        = string
                  match_criteria    = string
                  match_str         = list(string)
                  string_group_refs = list(string)
                }
              ))
            }
          ))
          name = string
        }
      ))
      default_auth_profile_ref = string
    }
  ))
  default = []
}

variable "authorization_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      authz_rules = list(object(
        {
          action = set(object(
            {
              status_code = string
              type        = string
            }
          ))
          enable = bool
          index  = number
          match = set(object(
            {
              attr_matches = list(object(
                {
                  attribute_name = string
                  attribute_value_list = set(object(
                    {
                      match_criteria    = string
                      match_str         = list(string)
                      string_group_refs = list(string)
                    }
                  ))
                }
              ))
              host_hdr = set(object(
                {
                  match_case     = string
                  match_criteria = string
                  value          = list(string)
                }
              ))
              method = set(object(
                {
                  match_criteria = string
                  methods        = list(string)
                }
              ))
              path = set(object(
                {
                  match_case        = string
                  match_criteria    = string
                  match_str         = list(string)
                  string_group_refs = list(string)
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
resource "avi_ssopolicy" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  type       = var.type
  uuid       = var.uuid

  dynamic "authentication_policy" {
    for_each = var.authentication_policy
    content {
      default_auth_profile_ref = authentication_policy.value["default_auth_profile_ref"]

      dynamic "authn_rules" {
        for_each = authentication_policy.value.authn_rules
        content {
          enable = authn_rules.value["enable"]
          index  = authn_rules.value["index"]
          name   = authn_rules.value["name"]

          dynamic "action" {
            for_each = authn_rules.value.action
            content {
              type = action.value["type"]
            }
          }

          dynamic "match" {
            for_each = authn_rules.value.match
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

              dynamic "host_hdr" {
                for_each = match.value.host_hdr
                content {
                  match_case     = host_hdr.value["match_case"]
                  match_criteria = host_hdr.value["match_criteria"]
                  value          = host_hdr.value["value"]
                }
              }

              dynamic "path" {
                for_each = match.value.path
                content {
                  match_case        = path.value["match_case"]
                  match_criteria    = path.value["match_criteria"]
                  match_str         = path.value["match_str"]
                  string_group_refs = path.value["string_group_refs"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "authorization_policy" {
    for_each = var.authorization_policy
    content {

      dynamic "authz_rules" {
        for_each = authorization_policy.value.authz_rules
        content {
          enable = authz_rules.value["enable"]
          index  = authz_rules.value["index"]
          name   = authz_rules.value["name"]

          dynamic "action" {
            for_each = authz_rules.value.action
            content {
              status_code = action.value["status_code"]
              type        = action.value["type"]
            }
          }

          dynamic "match" {
            for_each = authz_rules.value.match
            content {

              dynamic "attr_matches" {
                for_each = match.value.attr_matches
                content {
                  attribute_name = attr_matches.value["attribute_name"]

                  dynamic "attribute_value_list" {
                    for_each = attr_matches.value.attribute_value_list
                    content {
                      match_criteria    = attribute_value_list.value["match_criteria"]
                      match_str         = attribute_value_list.value["match_str"]
                      string_group_refs = attribute_value_list.value["string_group_refs"]
                    }
                  }

                }
              }

              dynamic "host_hdr" {
                for_each = match.value.host_hdr
                content {
                  match_case     = host_hdr.value["match_case"]
                  match_criteria = host_hdr.value["match_criteria"]
                  value          = host_hdr.value["value"]
                }
              }

              dynamic "method" {
                for_each = match.value.method
                content {
                  match_criteria = method.value["match_criteria"]
                  methods        = method.value["methods"]
                }
              }

              dynamic "path" {
                for_each = match.value.path
                content {
                  match_case        = path.value["match_case"]
                  match_criteria    = path.value["match_criteria"]
                  match_str         = path.value["match_str"]
                  string_group_refs = path.value["string_group_refs"]
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
output "id" {
  description = "returns a string"
  value       = avi_ssopolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_ssopolicy.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_ssopolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_ssopolicy.this.uuid
}

output "this" {
  value = avi_ssopolicy.this
}
```

[top](#index)