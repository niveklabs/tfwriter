# avi_wafpolicy

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
module "avi_wafpolicy" {
  source = "./modules/avi/r/avi_wafpolicy"

  # allow_mode_delegation - (optional) is a type of bool
  allow_mode_delegation = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # enable_app_learning - (optional) is a type of bool
  enable_app_learning = null
  # failure_mode - (optional) is a type of string
  failure_mode = null
  # mode - (optional) is a type of string
  mode = null
  # name - (required) is a type of string
  name = null
  # paranoia_level - (optional) is a type of string
  paranoia_level = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # waf_crs_ref - (optional) is a type of string
  waf_crs_ref = null
  # waf_profile_ref - (optional) is a type of string
  waf_profile_ref = null

  crs_groups = [{
    enable = null
    exclude_list = [{
      client_subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      description   = null
      match_element = null
      match_element_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_match_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_path = null
    }]
    index = null
    name  = null
    rules = [{
      enable = null
      exclude_list = [{
        client_subnet = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        description   = null
        match_element = null
        match_element_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_match_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_path = null
      }]
      index   = null
      mode    = null
      name    = null
      rule    = null
      rule_id = null
      tags    = []
    }]
  }]

  positive_security_model = [{
    group_refs = []
  }]

  post_crs_groups = [{
    enable = null
    exclude_list = [{
      client_subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      description   = null
      match_element = null
      match_element_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_match_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_path = null
    }]
    index = null
    name  = null
    rules = [{
      enable = null
      exclude_list = [{
        client_subnet = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        description   = null
        match_element = null
        match_element_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_match_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_path = null
      }]
      index   = null
      mode    = null
      name    = null
      rule    = null
      rule_id = null
      tags    = []
    }]
  }]

  pre_crs_groups = [{
    enable = null
    exclude_list = [{
      client_subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      description   = null
      match_element = null
      match_element_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_match_criteria = [{
        match_case = null
        match_op   = null
      }]
      uri_path = null
    }]
    index = null
    name  = null
    rules = [{
      enable = null
      exclude_list = [{
        client_subnet = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        description   = null
        match_element = null
        match_element_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_match_criteria = [{
          match_case = null
          match_op   = null
        }]
        uri_path = null
      }]
      index   = null
      mode    = null
      name    = null
      rule    = null
      rule_id = null
      tags    = []
    }]
  }]

  whitelist = [{
    rules = [{
      actions     = []
      description = null
      enable      = null
      index       = null
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
        cookie = [{
          match_case     = null
          match_criteria = null
          name           = null
          value          = null
        }]
        hdrs = [{
          hdr            = null
          match_case     = null
          match_criteria = null
          value          = []
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
        protocol = [{
          match_criteria = null
          protocols      = null
        }]
        query = [{
          match_case        = null
          match_criteria    = null
          match_str         = []
          string_group_refs = []
        }]
        version = [{
          match_criteria = null
          versions       = []
        }]
        vs_port = [{
          match_criteria = null
          ports          = []
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
variable "allow_mode_delegation" {
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

variable "enable_app_learning" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "failure_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "paranoia_level" {
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

variable "waf_crs_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "waf_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "crs_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enable = bool
      exclude_list = list(object(
        {
          client_subnet = set(object(
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
          description   = string
          match_element = string
          match_element_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_match_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_path = string
        }
      ))
      index = number
      name  = string
      rules = list(object(
        {
          enable = bool
          exclude_list = list(object(
            {
              client_subnet = set(object(
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
              description   = string
              match_element = string
              match_element_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_match_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_path = string
            }
          ))
          index   = number
          mode    = string
          name    = string
          rule    = string
          rule_id = string
          tags    = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "positive_security_model" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      group_refs = list(string)
    }
  ))
  default = []
}

variable "post_crs_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enable = bool
      exclude_list = list(object(
        {
          client_subnet = set(object(
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
          description   = string
          match_element = string
          match_element_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_match_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_path = string
        }
      ))
      index = number
      name  = string
      rules = list(object(
        {
          enable = bool
          exclude_list = list(object(
            {
              client_subnet = set(object(
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
              description   = string
              match_element = string
              match_element_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_match_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_path = string
            }
          ))
          index   = number
          mode    = string
          name    = string
          rule    = string
          rule_id = string
          tags    = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "pre_crs_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enable = bool
      exclude_list = list(object(
        {
          client_subnet = set(object(
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
          description   = string
          match_element = string
          match_element_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_match_criteria = set(object(
            {
              match_case = string
              match_op   = string
            }
          ))
          uri_path = string
        }
      ))
      index = number
      name  = string
      rules = list(object(
        {
          enable = bool
          exclude_list = list(object(
            {
              client_subnet = set(object(
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
              description   = string
              match_element = string
              match_element_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_match_criteria = set(object(
                {
                  match_case = string
                  match_op   = string
                }
              ))
              uri_path = string
            }
          ))
          index   = number
          mode    = string
          name    = string
          rule    = string
          rule_id = string
          tags    = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "whitelist" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      rules = list(object(
        {
          actions     = list(string)
          description = string
          enable      = bool
          index       = number
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
              cookie = set(object(
                {
                  match_case     = string
                  match_criteria = string
                  name           = string
                  value          = string
                }
              ))
              hdrs = list(object(
                {
                  hdr            = string
                  match_case     = string
                  match_criteria = string
                  value          = list(string)
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
              protocol = set(object(
                {
                  match_criteria = string
                  protocols      = string
                }
              ))
              query = set(object(
                {
                  match_case        = string
                  match_criteria    = string
                  match_str         = list(string)
                  string_group_refs = list(string)
                }
              ))
              version = set(object(
                {
                  match_criteria = string
                  versions       = list(string)
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
resource "avi_wafpolicy" "this" {
  # allow_mode_delegation - (optional) is a type of bool
  allow_mode_delegation = var.allow_mode_delegation
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # enable_app_learning - (optional) is a type of bool
  enable_app_learning = var.enable_app_learning
  # failure_mode - (optional) is a type of string
  failure_mode = var.failure_mode
  # mode - (optional) is a type of string
  mode = var.mode
  # name - (required) is a type of string
  name = var.name
  # paranoia_level - (optional) is a type of string
  paranoia_level = var.paranoia_level
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # waf_crs_ref - (optional) is a type of string
  waf_crs_ref = var.waf_crs_ref
  # waf_profile_ref - (optional) is a type of string
  waf_profile_ref = var.waf_profile_ref

  dynamic "crs_groups" {
    for_each = var.crs_groups
    content {
      # enable - (optional) is a type of bool
      enable = crs_groups.value["enable"]
      # index - (required) is a type of number
      index = crs_groups.value["index"]
      # name - (optional) is a type of string
      name = crs_groups.value["name"]

      dynamic "exclude_list" {
        for_each = crs_groups.value.exclude_list
        content {
          # description - (optional) is a type of string
          description = exclude_list.value["description"]
          # match_element - (optional) is a type of string
          match_element = exclude_list.value["match_element"]
          # uri_path - (optional) is a type of string
          uri_path = exclude_list.value["uri_path"]

          dynamic "client_subnet" {
            for_each = exclude_list.value.client_subnet
            content {
              # mask - (required) is a type of number
              mask = client_subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = client_subnet.value.ip_addr
                content {
                  # addr - (required) is a type of string
                  addr = ip_addr.value["addr"]
                  # type - (required) is a type of string
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "match_element_criteria" {
            for_each = exclude_list.value.match_element_criteria
            content {
              # match_case - (optional) is a type of string
              match_case = match_element_criteria.value["match_case"]
              # match_op - (optional) is a type of string
              match_op = match_element_criteria.value["match_op"]
            }
          }

          dynamic "uri_match_criteria" {
            for_each = exclude_list.value.uri_match_criteria
            content {
              # match_case - (optional) is a type of string
              match_case = uri_match_criteria.value["match_case"]
              # match_op - (optional) is a type of string
              match_op = uri_match_criteria.value["match_op"]
            }
          }

        }
      }

      dynamic "rules" {
        for_each = crs_groups.value.rules
        content {
          # enable - (optional) is a type of bool
          enable = rules.value["enable"]
          # index - (required) is a type of number
          index = rules.value["index"]
          # mode - (optional) is a type of string
          mode = rules.value["mode"]
          # name - (optional) is a type of string
          name = rules.value["name"]
          # rule - (optional) is a type of string
          rule = rules.value["rule"]
          # rule_id - (optional) is a type of string
          rule_id = rules.value["rule_id"]
          # tags - (optional) is a type of list of string
          tags = rules.value["tags"]

          dynamic "exclude_list" {
            for_each = rules.value.exclude_list
            content {
              # description - (optional) is a type of string
              description = exclude_list.value["description"]
              # match_element - (optional) is a type of string
              match_element = exclude_list.value["match_element"]
              # uri_path - (optional) is a type of string
              uri_path = exclude_list.value["uri_path"]

              dynamic "client_subnet" {
                for_each = exclude_list.value.client_subnet
                content {
                  # mask - (required) is a type of number
                  mask = client_subnet.value["mask"]

                  dynamic "ip_addr" {
                    for_each = client_subnet.value.ip_addr
                    content {
                      # addr - (required) is a type of string
                      addr = ip_addr.value["addr"]
                      # type - (required) is a type of string
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "match_element_criteria" {
                for_each = exclude_list.value.match_element_criteria
                content {
                  # match_case - (optional) is a type of string
                  match_case = match_element_criteria.value["match_case"]
                  # match_op - (optional) is a type of string
                  match_op = match_element_criteria.value["match_op"]
                }
              }

              dynamic "uri_match_criteria" {
                for_each = exclude_list.value.uri_match_criteria
                content {
                  # match_case - (optional) is a type of string
                  match_case = uri_match_criteria.value["match_case"]
                  # match_op - (optional) is a type of string
                  match_op = uri_match_criteria.value["match_op"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "positive_security_model" {
    for_each = var.positive_security_model
    content {
      # group_refs - (optional) is a type of list of string
      group_refs = positive_security_model.value["group_refs"]
    }
  }

  dynamic "post_crs_groups" {
    for_each = var.post_crs_groups
    content {
      # enable - (optional) is a type of bool
      enable = post_crs_groups.value["enable"]
      # index - (required) is a type of number
      index = post_crs_groups.value["index"]
      # name - (optional) is a type of string
      name = post_crs_groups.value["name"]

      dynamic "exclude_list" {
        for_each = post_crs_groups.value.exclude_list
        content {
          # description - (optional) is a type of string
          description = exclude_list.value["description"]
          # match_element - (optional) is a type of string
          match_element = exclude_list.value["match_element"]
          # uri_path - (optional) is a type of string
          uri_path = exclude_list.value["uri_path"]

          dynamic "client_subnet" {
            for_each = exclude_list.value.client_subnet
            content {
              # mask - (required) is a type of number
              mask = client_subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = client_subnet.value.ip_addr
                content {
                  # addr - (required) is a type of string
                  addr = ip_addr.value["addr"]
                  # type - (required) is a type of string
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "match_element_criteria" {
            for_each = exclude_list.value.match_element_criteria
            content {
              # match_case - (optional) is a type of string
              match_case = match_element_criteria.value["match_case"]
              # match_op - (optional) is a type of string
              match_op = match_element_criteria.value["match_op"]
            }
          }

          dynamic "uri_match_criteria" {
            for_each = exclude_list.value.uri_match_criteria
            content {
              # match_case - (optional) is a type of string
              match_case = uri_match_criteria.value["match_case"]
              # match_op - (optional) is a type of string
              match_op = uri_match_criteria.value["match_op"]
            }
          }

        }
      }

      dynamic "rules" {
        for_each = post_crs_groups.value.rules
        content {
          # enable - (optional) is a type of bool
          enable = rules.value["enable"]
          # index - (required) is a type of number
          index = rules.value["index"]
          # mode - (optional) is a type of string
          mode = rules.value["mode"]
          # name - (optional) is a type of string
          name = rules.value["name"]
          # rule - (optional) is a type of string
          rule = rules.value["rule"]
          # rule_id - (optional) is a type of string
          rule_id = rules.value["rule_id"]
          # tags - (optional) is a type of list of string
          tags = rules.value["tags"]

          dynamic "exclude_list" {
            for_each = rules.value.exclude_list
            content {
              # description - (optional) is a type of string
              description = exclude_list.value["description"]
              # match_element - (optional) is a type of string
              match_element = exclude_list.value["match_element"]
              # uri_path - (optional) is a type of string
              uri_path = exclude_list.value["uri_path"]

              dynamic "client_subnet" {
                for_each = exclude_list.value.client_subnet
                content {
                  # mask - (required) is a type of number
                  mask = client_subnet.value["mask"]

                  dynamic "ip_addr" {
                    for_each = client_subnet.value.ip_addr
                    content {
                      # addr - (required) is a type of string
                      addr = ip_addr.value["addr"]
                      # type - (required) is a type of string
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "match_element_criteria" {
                for_each = exclude_list.value.match_element_criteria
                content {
                  # match_case - (optional) is a type of string
                  match_case = match_element_criteria.value["match_case"]
                  # match_op - (optional) is a type of string
                  match_op = match_element_criteria.value["match_op"]
                }
              }

              dynamic "uri_match_criteria" {
                for_each = exclude_list.value.uri_match_criteria
                content {
                  # match_case - (optional) is a type of string
                  match_case = uri_match_criteria.value["match_case"]
                  # match_op - (optional) is a type of string
                  match_op = uri_match_criteria.value["match_op"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "pre_crs_groups" {
    for_each = var.pre_crs_groups
    content {
      # enable - (optional) is a type of bool
      enable = pre_crs_groups.value["enable"]
      # index - (required) is a type of number
      index = pre_crs_groups.value["index"]
      # name - (optional) is a type of string
      name = pre_crs_groups.value["name"]

      dynamic "exclude_list" {
        for_each = pre_crs_groups.value.exclude_list
        content {
          # description - (optional) is a type of string
          description = exclude_list.value["description"]
          # match_element - (optional) is a type of string
          match_element = exclude_list.value["match_element"]
          # uri_path - (optional) is a type of string
          uri_path = exclude_list.value["uri_path"]

          dynamic "client_subnet" {
            for_each = exclude_list.value.client_subnet
            content {
              # mask - (required) is a type of number
              mask = client_subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = client_subnet.value.ip_addr
                content {
                  # addr - (required) is a type of string
                  addr = ip_addr.value["addr"]
                  # type - (required) is a type of string
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "match_element_criteria" {
            for_each = exclude_list.value.match_element_criteria
            content {
              # match_case - (optional) is a type of string
              match_case = match_element_criteria.value["match_case"]
              # match_op - (optional) is a type of string
              match_op = match_element_criteria.value["match_op"]
            }
          }

          dynamic "uri_match_criteria" {
            for_each = exclude_list.value.uri_match_criteria
            content {
              # match_case - (optional) is a type of string
              match_case = uri_match_criteria.value["match_case"]
              # match_op - (optional) is a type of string
              match_op = uri_match_criteria.value["match_op"]
            }
          }

        }
      }

      dynamic "rules" {
        for_each = pre_crs_groups.value.rules
        content {
          # enable - (optional) is a type of bool
          enable = rules.value["enable"]
          # index - (required) is a type of number
          index = rules.value["index"]
          # mode - (optional) is a type of string
          mode = rules.value["mode"]
          # name - (optional) is a type of string
          name = rules.value["name"]
          # rule - (optional) is a type of string
          rule = rules.value["rule"]
          # rule_id - (optional) is a type of string
          rule_id = rules.value["rule_id"]
          # tags - (optional) is a type of list of string
          tags = rules.value["tags"]

          dynamic "exclude_list" {
            for_each = rules.value.exclude_list
            content {
              # description - (optional) is a type of string
              description = exclude_list.value["description"]
              # match_element - (optional) is a type of string
              match_element = exclude_list.value["match_element"]
              # uri_path - (optional) is a type of string
              uri_path = exclude_list.value["uri_path"]

              dynamic "client_subnet" {
                for_each = exclude_list.value.client_subnet
                content {
                  # mask - (required) is a type of number
                  mask = client_subnet.value["mask"]

                  dynamic "ip_addr" {
                    for_each = client_subnet.value.ip_addr
                    content {
                      # addr - (required) is a type of string
                      addr = ip_addr.value["addr"]
                      # type - (required) is a type of string
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "match_element_criteria" {
                for_each = exclude_list.value.match_element_criteria
                content {
                  # match_case - (optional) is a type of string
                  match_case = match_element_criteria.value["match_case"]
                  # match_op - (optional) is a type of string
                  match_op = match_element_criteria.value["match_op"]
                }
              }

              dynamic "uri_match_criteria" {
                for_each = exclude_list.value.uri_match_criteria
                content {
                  # match_case - (optional) is a type of string
                  match_case = uri_match_criteria.value["match_case"]
                  # match_op - (optional) is a type of string
                  match_op = uri_match_criteria.value["match_op"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "whitelist" {
    for_each = var.whitelist
    content {

      dynamic "rules" {
        for_each = whitelist.value.rules
        content {
          # actions - (optional) is a type of list of string
          actions = rules.value["actions"]
          # description - (optional) is a type of string
          description = rules.value["description"]
          # enable - (optional) is a type of bool
          enable = rules.value["enable"]
          # index - (optional) is a type of number
          index = rules.value["index"]
          # name - (optional) is a type of string
          name = rules.value["name"]

          dynamic "match" {
            for_each = rules.value.match
            content {

              dynamic "client_ip" {
                for_each = match.value.client_ip
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

              dynamic "cookie" {
                for_each = match.value.cookie
                content {
                  # match_case - (optional) is a type of string
                  match_case = cookie.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = cookie.value["match_criteria"]
                  # name - (required) is a type of string
                  name = cookie.value["name"]
                  # value - (optional) is a type of string
                  value = cookie.value["value"]
                }
              }

              dynamic "hdrs" {
                for_each = match.value.hdrs
                content {
                  # hdr - (required) is a type of string
                  hdr = hdrs.value["hdr"]
                  # match_case - (optional) is a type of string
                  match_case = hdrs.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = hdrs.value["match_criteria"]
                  # value - (optional) is a type of list of string
                  value = hdrs.value["value"]
                }
              }

              dynamic "host_hdr" {
                for_each = match.value.host_hdr
                content {
                  # match_case - (optional) is a type of string
                  match_case = host_hdr.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = host_hdr.value["match_criteria"]
                  # value - (optional) is a type of list of string
                  value = host_hdr.value["value"]
                }
              }

              dynamic "method" {
                for_each = match.value.method
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = method.value["match_criteria"]
                  # methods - (optional) is a type of list of string
                  methods = method.value["methods"]
                }
              }

              dynamic "path" {
                for_each = match.value.path
                content {
                  # match_case - (optional) is a type of string
                  match_case = path.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = path.value["match_criteria"]
                  # match_str - (optional) is a type of list of string
                  match_str = path.value["match_str"]
                  # string_group_refs - (optional) is a type of list of string
                  string_group_refs = path.value["string_group_refs"]
                }
              }

              dynamic "protocol" {
                for_each = match.value.protocol
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = protocol.value["match_criteria"]
                  # protocols - (required) is a type of string
                  protocols = protocol.value["protocols"]
                }
              }

              dynamic "query" {
                for_each = match.value.query
                content {
                  # match_case - (optional) is a type of string
                  match_case = query.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = query.value["match_criteria"]
                  # match_str - (optional) is a type of list of string
                  match_str = query.value["match_str"]
                  # string_group_refs - (optional) is a type of list of string
                  string_group_refs = query.value["string_group_refs"]
                }
              }

              dynamic "version" {
                for_each = match.value.version
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = version.value["match_criteria"]
                  # versions - (optional) is a type of list of string
                  versions = version.value["versions"]
                }
              }

              dynamic "vs_port" {
                for_each = match.value.vs_port
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = vs_port.value["match_criteria"]
                  # ports - (optional) is a type of list of number
                  ports = vs_port.value["ports"]
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
  value       = avi_wafpolicy.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_wafpolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_wafpolicy.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_wafpolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_wafpolicy.this.uuid
}

output "waf_crs_ref" {
  description = "returns a string"
  value       = avi_wafpolicy.this.waf_crs_ref
}

output "waf_profile_ref" {
  description = "returns a string"
  value       = avi_wafpolicy.this.waf_profile_ref
}

output "this" {
  value = avi_wafpolicy.this
}
```

[top](#index)