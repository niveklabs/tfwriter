# avi_httppolicyset

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
module "avi_httppolicyset" {
  source = "./modules/avi/r/avi_httppolicyset"

  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # is_internal_policy - (optional) is a type of bool
  is_internal_policy = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  http_request_policy = [{
    rules = [{
      all_headers = null
      enable      = null
      hdr_action = [{
        action = null
        cookie = [{
          name  = null
          value = null
        }]
        hdr = [{
          name = null
          value = [{
            val = null
            var = null
          }]
        }]
      }]
      index = null
      log   = null
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
      redirect_action = [{
        host = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        keep_query = null
        path = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        port        = null
        protocol    = null
        status_code = null
      }]
      rewrite_url_action = [{
        host_hdr = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        path = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        query = [{
          add_string = null
          keep_query = null
        }]
      }]
      switching_action = [{
        action = null
        file = [{
          content_type = null
          file_content = null
        }]
        pool_group_ref = null
        pool_ref       = null
        server = [{
          hostname = null
          ip = [{
            addr = null
            type = null
          }]
          port = null
        }]
        status_code = null
      }]
    }]
  }]

  http_response_policy = [{
    rules = [{
      all_headers = null
      enable      = null
      hdr_action = [{
        action = null
        cookie = [{
          name  = null
          value = null
        }]
        hdr = [{
          name = null
          value = [{
            val = null
            var = null
          }]
        }]
      }]
      index = null
      loc_hdr_action = [{
        host = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        keep_query = null
        path = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        port     = null
        protocol = null
      }]
      log = null
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
        loc_hdr = [{
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
        rsp_hdrs = [{
          hdr            = null
          match_case     = null
          match_criteria = null
          value          = []
        }]
        status = [{
          match_criteria = null
          ranges = [{
            begin = null
            end   = null
          }]
          status_codes = []
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

  http_security_policy = [{
    rules = [{
      action = [{
        action = null
        file = [{
          content_type = null
          file_content = null
        }]
        https_port = null
        rate_profile = [{
          action = [{
            file = [{
              content_type = null
              file_content = null
            }]
            redirect = [{
              host = [{
                tokens = [{
                  end_index   = null
                  start_index = null
                  str_value   = null
                  type        = null
                }]
                type = null
              }]
              keep_query = null
              path = [{
                tokens = [{
                  end_index   = null
                  start_index = null
                  str_value   = null
                  type        = null
                }]
                type = null
              }]
              port        = null
              protocol    = null
              status_code = null
            }]
            status_code = null
            type        = null
          }]
          per_client_ip = null
          per_uri_path  = null
          rate_limiter = [{
            burst_sz = null
            count    = null
            name     = null
            period   = null
          }]
        }]
        status_code = null
      }]
      enable = null
      index  = null
      log    = null
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

variable "is_internal_policy" {
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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_request_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      rules = list(object(
        {
          all_headers = bool
          enable      = bool
          hdr_action = list(object(
            {
              action = string
              cookie = set(object(
                {
                  name  = string
                  value = string
                }
              ))
              hdr = set(object(
                {
                  name = string
                  value = set(object(
                    {
                      val = string
                      var = string
                    }
                  ))
                }
              ))
            }
          ))
          index = number
          log   = bool
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
          redirect_action = set(object(
            {
              host = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              keep_query = bool
              path = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              port        = number
              protocol    = string
              status_code = string
            }
          ))
          rewrite_url_action = set(object(
            {
              host_hdr = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              path = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              query = set(object(
                {
                  add_string = string
                  keep_query = bool
                }
              ))
            }
          ))
          switching_action = set(object(
            {
              action = string
              file = set(object(
                {
                  content_type = string
                  file_content = string
                }
              ))
              pool_group_ref = string
              pool_ref       = string
              server = set(object(
                {
                  hostname = string
                  ip = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  port = number
                }
              ))
              status_code = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "http_response_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      rules = list(object(
        {
          all_headers = bool
          enable      = bool
          hdr_action = list(object(
            {
              action = string
              cookie = set(object(
                {
                  name  = string
                  value = string
                }
              ))
              hdr = set(object(
                {
                  name = string
                  value = set(object(
                    {
                      val = string
                      var = string
                    }
                  ))
                }
              ))
            }
          ))
          index = number
          loc_hdr_action = set(object(
            {
              host = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              keep_query = bool
              path = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              port     = number
              protocol = string
            }
          ))
          log = bool
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
              loc_hdr = set(object(
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
              rsp_hdrs = list(object(
                {
                  hdr            = string
                  match_case     = string
                  match_criteria = string
                  value          = list(string)
                }
              ))
              status = set(object(
                {
                  match_criteria = string
                  ranges = list(object(
                    {
                      begin = number
                      end   = number
                    }
                  ))
                  status_codes = list(number)
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

variable "http_security_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      rules = list(object(
        {
          action = set(object(
            {
              action = string
              file = set(object(
                {
                  content_type = string
                  file_content = string
                }
              ))
              https_port = number
              rate_profile = set(object(
                {
                  action = set(object(
                    {
                      file = set(object(
                        {
                          content_type = string
                          file_content = string
                        }
                      ))
                      redirect = set(object(
                        {
                          host = set(object(
                            {
                              tokens = list(object(
                                {
                                  end_index   = number
                                  start_index = number
                                  str_value   = string
                                  type        = string
                                }
                              ))
                              type = string
                            }
                          ))
                          keep_query = bool
                          path = set(object(
                            {
                              tokens = list(object(
                                {
                                  end_index   = number
                                  start_index = number
                                  str_value   = string
                                  type        = string
                                }
                              ))
                              type = string
                            }
                          ))
                          port        = number
                          protocol    = string
                          status_code = string
                        }
                      ))
                      status_code = string
                      type        = string
                    }
                  ))
                  per_client_ip = bool
                  per_uri_path  = bool
                  rate_limiter = set(object(
                    {
                      burst_sz = number
                      count    = number
                      name     = string
                      period   = number
                    }
                  ))
                }
              ))
              status_code = string
            }
          ))
          enable = bool
          index  = number
          log    = bool
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
resource "avi_httppolicyset" "this" {
  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = var.cloud_config_cksum
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # is_internal_policy - (optional) is a type of bool
  is_internal_policy = var.is_internal_policy
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "http_request_policy" {
    for_each = var.http_request_policy
    content {

      dynamic "rules" {
        for_each = http_request_policy.value.rules
        content {
          # all_headers - (optional) is a type of bool
          all_headers = rules.value["all_headers"]
          # enable - (required) is a type of bool
          enable = rules.value["enable"]
          # index - (required) is a type of number
          index = rules.value["index"]
          # log - (optional) is a type of bool
          log = rules.value["log"]
          # name - (required) is a type of string
          name = rules.value["name"]

          dynamic "hdr_action" {
            for_each = rules.value.hdr_action
            content {
              # action - (required) is a type of string
              action = hdr_action.value["action"]

              dynamic "cookie" {
                for_each = hdr_action.value.cookie
                content {
                  # name - (optional) is a type of string
                  name = cookie.value["name"]
                  # value - (optional) is a type of string
                  value = cookie.value["value"]
                }
              }

              dynamic "hdr" {
                for_each = hdr_action.value.hdr
                content {
                  # name - (optional) is a type of string
                  name = hdr.value["name"]

                  dynamic "value" {
                    for_each = hdr.value.value
                    content {
                      # val - (optional) is a type of string
                      val = value.value["val"]
                      # var - (optional) is a type of string
                      var = value.value["var"]
                    }
                  }

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

          dynamic "redirect_action" {
            for_each = rules.value.redirect_action
            content {
              # keep_query - (optional) is a type of bool
              keep_query = redirect_action.value["keep_query"]
              # port - (optional) is a type of number
              port = redirect_action.value["port"]
              # protocol - (required) is a type of string
              protocol = redirect_action.value["protocol"]
              # status_code - (optional) is a type of string
              status_code = redirect_action.value["status_code"]

              dynamic "host" {
                for_each = redirect_action.value.host
                content {
                  # type - (required) is a type of string
                  type = host.value["type"]

                  dynamic "tokens" {
                    for_each = host.value.tokens
                    content {
                      # end_index - (optional) is a type of number
                      end_index = tokens.value["end_index"]
                      # start_index - (optional) is a type of number
                      start_index = tokens.value["start_index"]
                      # str_value - (optional) is a type of string
                      str_value = tokens.value["str_value"]
                      # type - (required) is a type of string
                      type = tokens.value["type"]
                    }
                  }

                }
              }

              dynamic "path" {
                for_each = redirect_action.value.path
                content {
                  # type - (required) is a type of string
                  type = path.value["type"]

                  dynamic "tokens" {
                    for_each = path.value.tokens
                    content {
                      # end_index - (optional) is a type of number
                      end_index = tokens.value["end_index"]
                      # start_index - (optional) is a type of number
                      start_index = tokens.value["start_index"]
                      # str_value - (optional) is a type of string
                      str_value = tokens.value["str_value"]
                      # type - (required) is a type of string
                      type = tokens.value["type"]
                    }
                  }

                }
              }

            }
          }

          dynamic "rewrite_url_action" {
            for_each = rules.value.rewrite_url_action
            content {

              dynamic "host_hdr" {
                for_each = rewrite_url_action.value.host_hdr
                content {
                  # type - (required) is a type of string
                  type = host_hdr.value["type"]

                  dynamic "tokens" {
                    for_each = host_hdr.value.tokens
                    content {
                      # end_index - (optional) is a type of number
                      end_index = tokens.value["end_index"]
                      # start_index - (optional) is a type of number
                      start_index = tokens.value["start_index"]
                      # str_value - (optional) is a type of string
                      str_value = tokens.value["str_value"]
                      # type - (required) is a type of string
                      type = tokens.value["type"]
                    }
                  }

                }
              }

              dynamic "path" {
                for_each = rewrite_url_action.value.path
                content {
                  # type - (required) is a type of string
                  type = path.value["type"]

                  dynamic "tokens" {
                    for_each = path.value.tokens
                    content {
                      # end_index - (optional) is a type of number
                      end_index = tokens.value["end_index"]
                      # start_index - (optional) is a type of number
                      start_index = tokens.value["start_index"]
                      # str_value - (optional) is a type of string
                      str_value = tokens.value["str_value"]
                      # type - (required) is a type of string
                      type = tokens.value["type"]
                    }
                  }

                }
              }

              dynamic "query" {
                for_each = rewrite_url_action.value.query
                content {
                  # add_string - (optional) is a type of string
                  add_string = query.value["add_string"]
                  # keep_query - (optional) is a type of bool
                  keep_query = query.value["keep_query"]
                }
              }

            }
          }

          dynamic "switching_action" {
            for_each = rules.value.switching_action
            content {
              # action - (required) is a type of string
              action = switching_action.value["action"]
              # pool_group_ref - (optional) is a type of string
              pool_group_ref = switching_action.value["pool_group_ref"]
              # pool_ref - (optional) is a type of string
              pool_ref = switching_action.value["pool_ref"]
              # status_code - (optional) is a type of string
              status_code = switching_action.value["status_code"]

              dynamic "file" {
                for_each = switching_action.value.file
                content {
                  # content_type - (required) is a type of string
                  content_type = file.value["content_type"]
                  # file_content - (required) is a type of string
                  file_content = file.value["file_content"]
                }
              }

              dynamic "server" {
                for_each = switching_action.value.server
                content {
                  # hostname - (optional) is a type of string
                  hostname = server.value["hostname"]
                  # port - (optional) is a type of number
                  port = server.value["port"]

                  dynamic "ip" {
                    for_each = server.value.ip
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
  }

  dynamic "http_response_policy" {
    for_each = var.http_response_policy
    content {

      dynamic "rules" {
        for_each = http_response_policy.value.rules
        content {
          # all_headers - (optional) is a type of bool
          all_headers = rules.value["all_headers"]
          # enable - (required) is a type of bool
          enable = rules.value["enable"]
          # index - (required) is a type of number
          index = rules.value["index"]
          # log - (optional) is a type of bool
          log = rules.value["log"]
          # name - (required) is a type of string
          name = rules.value["name"]

          dynamic "hdr_action" {
            for_each = rules.value.hdr_action
            content {
              # action - (required) is a type of string
              action = hdr_action.value["action"]

              dynamic "cookie" {
                for_each = hdr_action.value.cookie
                content {
                  # name - (optional) is a type of string
                  name = cookie.value["name"]
                  # value - (optional) is a type of string
                  value = cookie.value["value"]
                }
              }

              dynamic "hdr" {
                for_each = hdr_action.value.hdr
                content {
                  # name - (optional) is a type of string
                  name = hdr.value["name"]

                  dynamic "value" {
                    for_each = hdr.value.value
                    content {
                      # val - (optional) is a type of string
                      val = value.value["val"]
                      # var - (optional) is a type of string
                      var = value.value["var"]
                    }
                  }

                }
              }

            }
          }

          dynamic "loc_hdr_action" {
            for_each = rules.value.loc_hdr_action
            content {
              # keep_query - (optional) is a type of bool
              keep_query = loc_hdr_action.value["keep_query"]
              # port - (optional) is a type of number
              port = loc_hdr_action.value["port"]
              # protocol - (required) is a type of string
              protocol = loc_hdr_action.value["protocol"]

              dynamic "host" {
                for_each = loc_hdr_action.value.host
                content {
                  # type - (required) is a type of string
                  type = host.value["type"]

                  dynamic "tokens" {
                    for_each = host.value.tokens
                    content {
                      # end_index - (optional) is a type of number
                      end_index = tokens.value["end_index"]
                      # start_index - (optional) is a type of number
                      start_index = tokens.value["start_index"]
                      # str_value - (optional) is a type of string
                      str_value = tokens.value["str_value"]
                      # type - (required) is a type of string
                      type = tokens.value["type"]
                    }
                  }

                }
              }

              dynamic "path" {
                for_each = loc_hdr_action.value.path
                content {
                  # type - (required) is a type of string
                  type = path.value["type"]

                  dynamic "tokens" {
                    for_each = path.value.tokens
                    content {
                      # end_index - (optional) is a type of number
                      end_index = tokens.value["end_index"]
                      # start_index - (optional) is a type of number
                      start_index = tokens.value["start_index"]
                      # str_value - (optional) is a type of string
                      str_value = tokens.value["str_value"]
                      # type - (required) is a type of string
                      type = tokens.value["type"]
                    }
                  }

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

              dynamic "loc_hdr" {
                for_each = match.value.loc_hdr
                content {
                  # match_case - (optional) is a type of string
                  match_case = loc_hdr.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = loc_hdr.value["match_criteria"]
                  # value - (optional) is a type of list of string
                  value = loc_hdr.value["value"]
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

              dynamic "rsp_hdrs" {
                for_each = match.value.rsp_hdrs
                content {
                  # hdr - (required) is a type of string
                  hdr = rsp_hdrs.value["hdr"]
                  # match_case - (optional) is a type of string
                  match_case = rsp_hdrs.value["match_case"]
                  # match_criteria - (required) is a type of string
                  match_criteria = rsp_hdrs.value["match_criteria"]
                  # value - (optional) is a type of list of string
                  value = rsp_hdrs.value["value"]
                }
              }

              dynamic "status" {
                for_each = match.value.status
                content {
                  # match_criteria - (required) is a type of string
                  match_criteria = status.value["match_criteria"]
                  # status_codes - (optional) is a type of list of number
                  status_codes = status.value["status_codes"]

                  dynamic "ranges" {
                    for_each = status.value.ranges
                    content {
                      # begin - (required) is a type of number
                      begin = ranges.value["begin"]
                      # end - (required) is a type of number
                      end = ranges.value["end"]
                    }
                  }

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

  dynamic "http_security_policy" {
    for_each = var.http_security_policy
    content {

      dynamic "rules" {
        for_each = http_security_policy.value.rules
        content {
          # enable - (required) is a type of bool
          enable = rules.value["enable"]
          # index - (required) is a type of number
          index = rules.value["index"]
          # log - (optional) is a type of bool
          log = rules.value["log"]
          # name - (required) is a type of string
          name = rules.value["name"]

          dynamic "action" {
            for_each = rules.value.action
            content {
              # action - (required) is a type of string
              action = action.value["action"]
              # https_port - (optional) is a type of number
              https_port = action.value["https_port"]
              # status_code - (optional) is a type of string
              status_code = action.value["status_code"]

              dynamic "file" {
                for_each = action.value.file
                content {
                  # content_type - (required) is a type of string
                  content_type = file.value["content_type"]
                  # file_content - (required) is a type of string
                  file_content = file.value["file_content"]
                }
              }

              dynamic "rate_profile" {
                for_each = action.value.rate_profile
                content {
                  # per_client_ip - (optional) is a type of bool
                  per_client_ip = rate_profile.value["per_client_ip"]
                  # per_uri_path - (optional) is a type of bool
                  per_uri_path = rate_profile.value["per_uri_path"]

                  dynamic "action" {
                    for_each = rate_profile.value.action
                    content {
                      # status_code - (optional) is a type of string
                      status_code = action.value["status_code"]
                      # type - (optional) is a type of string
                      type = action.value["type"]

                      dynamic "file" {
                        for_each = action.value.file
                        content {
                          # content_type - (required) is a type of string
                          content_type = file.value["content_type"]
                          # file_content - (required) is a type of string
                          file_content = file.value["file_content"]
                        }
                      }

                      dynamic "redirect" {
                        for_each = action.value.redirect
                        content {
                          # keep_query - (optional) is a type of bool
                          keep_query = redirect.value["keep_query"]
                          # port - (optional) is a type of number
                          port = redirect.value["port"]
                          # protocol - (required) is a type of string
                          protocol = redirect.value["protocol"]
                          # status_code - (optional) is a type of string
                          status_code = redirect.value["status_code"]

                          dynamic "host" {
                            for_each = redirect.value.host
                            content {
                              # type - (required) is a type of string
                              type = host.value["type"]

                              dynamic "tokens" {
                                for_each = host.value.tokens
                                content {
                                  # end_index - (optional) is a type of number
                                  end_index = tokens.value["end_index"]
                                  # start_index - (optional) is a type of number
                                  start_index = tokens.value["start_index"]
                                  # str_value - (optional) is a type of string
                                  str_value = tokens.value["str_value"]
                                  # type - (required) is a type of string
                                  type = tokens.value["type"]
                                }
                              }

                            }
                          }

                          dynamic "path" {
                            for_each = redirect.value.path
                            content {
                              # type - (required) is a type of string
                              type = path.value["type"]

                              dynamic "tokens" {
                                for_each = path.value.tokens
                                content {
                                  # end_index - (optional) is a type of number
                                  end_index = tokens.value["end_index"]
                                  # start_index - (optional) is a type of number
                                  start_index = tokens.value["start_index"]
                                  # str_value - (optional) is a type of string
                                  str_value = tokens.value["str_value"]
                                  # type - (required) is a type of string
                                  type = tokens.value["type"]
                                }
                              }

                            }
                          }

                        }
                      }

                    }
                  }

                  dynamic "rate_limiter" {
                    for_each = rate_profile.value.rate_limiter
                    content {
                      # burst_sz - (optional) is a type of number
                      burst_sz = rate_limiter.value["burst_sz"]
                      # count - (optional) is a type of number
                      count = rate_limiter.value["count"]
                      # name - (optional) is a type of string
                      name = rate_limiter.value["name"]
                      # period - (optional) is a type of number
                      period = rate_limiter.value["period"]
                    }
                  }

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
output "cloud_config_cksum" {
  description = "returns a string"
  value       = avi_httppolicyset.this.cloud_config_cksum
}

output "created_by" {
  description = "returns a string"
  value       = avi_httppolicyset.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_httppolicyset.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_httppolicyset.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_httppolicyset.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_httppolicyset.this.uuid
}

output "this" {
  value = avi_httppolicyset.this
}
```

[top](#index)