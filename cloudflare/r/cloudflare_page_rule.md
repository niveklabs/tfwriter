# cloudflare_page_rule

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_page_rule" {
  source = "./modules/cloudflare/r/cloudflare_page_rule"

  # priority - (optional) is a type of number
  priority = null
  # status - (optional) is a type of string
  status = null
  # target - (required) is a type of string
  target = null
  # zone_id - (required) is a type of string
  zone_id = null

  actions = [{
    always_online            = null
    always_use_https         = null
    automatic_https_rewrites = null
    browser_cache_ttl        = null
    browser_check            = null
    bypass_cache_on_cookie   = null
    cache_by_device_type     = null
    cache_deception_armor    = null
    cache_key_fields = [{
      cookie = [{
        check_presence = []
        include        = []
      }]
      header = [{
        check_presence = []
        exclude        = []
        include        = []
      }]
      host = [{
        resolved = null
      }]
      query_string = [{
        exclude = []
        ignore  = null
        include = []
      }]
      user = [{
        device_type = null
        geo         = null
        lang        = null
      }]
    }]
    cache_level     = null
    cache_on_cookie = null
    cache_ttl_by_status = [{
      codes = null
      ttl   = null
    }]
    disable_apps           = null
    disable_performance    = null
    disable_railgun        = null
    disable_security       = null
    edge_cache_ttl         = null
    email_obfuscation      = null
    explicit_cache_control = null
    forwarding_url = [{
      status_code = null
      url         = null
    }]
    host_header_override = null
    ip_geolocation       = null
    minify = [{
      css  = null
      html = null
      js   = null
    }]
    mirage                      = null
    opportunistic_encryption    = null
    origin_error_page_pass_thru = null
    polish                      = null
    resolve_override            = null
    respect_strong_etag         = null
    response_buffering          = null
    rocket_loader               = null
    security_level              = null
    server_side_exclude         = null
    sort_query_string_for_cache = null
    ssl                         = null
    true_client_ip_header       = null
    waf                         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "actions" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      always_online            = string
      always_use_https         = bool
      automatic_https_rewrites = string
      browser_cache_ttl        = string
      browser_check            = string
      bypass_cache_on_cookie   = string
      cache_by_device_type     = string
      cache_deception_armor    = string
      cache_key_fields = list(object(
        {
          cookie = list(object(
            {
              check_presence = set(string)
              include        = set(string)
            }
          ))
          header = list(object(
            {
              check_presence = set(string)
              exclude        = set(string)
              include        = set(string)
            }
          ))
          host = list(object(
            {
              resolved = bool
            }
          ))
          query_string = list(object(
            {
              exclude = set(string)
              ignore  = bool
              include = set(string)
            }
          ))
          user = list(object(
            {
              device_type = bool
              geo         = bool
              lang        = bool
            }
          ))
        }
      ))
      cache_level     = string
      cache_on_cookie = string
      cache_ttl_by_status = set(object(
        {
          codes = string
          ttl   = number
        }
      ))
      disable_apps           = bool
      disable_performance    = bool
      disable_railgun        = bool
      disable_security       = bool
      edge_cache_ttl         = number
      email_obfuscation      = string
      explicit_cache_control = string
      forwarding_url = list(object(
        {
          status_code = number
          url         = string
        }
      ))
      host_header_override = string
      ip_geolocation       = string
      minify = list(object(
        {
          css  = string
          html = string
          js   = string
        }
      ))
      mirage                      = string
      opportunistic_encryption    = string
      origin_error_page_pass_thru = string
      polish                      = string
      resolve_override            = string
      respect_strong_etag         = string
      response_buffering          = string
      rocket_loader               = string
      security_level              = string
      server_side_exclude         = string
      sort_query_string_for_cache = string
      ssl                         = string
      true_client_ip_header       = string
      waf                         = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_page_rule" "this" {
  # priority - (optional) is a type of number
  priority = var.priority
  # status - (optional) is a type of string
  status = var.status
  # target - (required) is a type of string
  target = var.target
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "actions" {
    for_each = var.actions
    content {
      # always_online - (optional) is a type of string
      always_online = actions.value["always_online"]
      # always_use_https - (optional) is a type of bool
      always_use_https = actions.value["always_use_https"]
      # automatic_https_rewrites - (optional) is a type of string
      automatic_https_rewrites = actions.value["automatic_https_rewrites"]
      # browser_cache_ttl - (optional) is a type of string
      browser_cache_ttl = actions.value["browser_cache_ttl"]
      # browser_check - (optional) is a type of string
      browser_check = actions.value["browser_check"]
      # bypass_cache_on_cookie - (optional) is a type of string
      bypass_cache_on_cookie = actions.value["bypass_cache_on_cookie"]
      # cache_by_device_type - (optional) is a type of string
      cache_by_device_type = actions.value["cache_by_device_type"]
      # cache_deception_armor - (optional) is a type of string
      cache_deception_armor = actions.value["cache_deception_armor"]
      # cache_level - (optional) is a type of string
      cache_level = actions.value["cache_level"]
      # cache_on_cookie - (optional) is a type of string
      cache_on_cookie = actions.value["cache_on_cookie"]
      # disable_apps - (optional) is a type of bool
      disable_apps = actions.value["disable_apps"]
      # disable_performance - (optional) is a type of bool
      disable_performance = actions.value["disable_performance"]
      # disable_railgun - (optional) is a type of bool
      disable_railgun = actions.value["disable_railgun"]
      # disable_security - (optional) is a type of bool
      disable_security = actions.value["disable_security"]
      # edge_cache_ttl - (optional) is a type of number
      edge_cache_ttl = actions.value["edge_cache_ttl"]
      # email_obfuscation - (optional) is a type of string
      email_obfuscation = actions.value["email_obfuscation"]
      # explicit_cache_control - (optional) is a type of string
      explicit_cache_control = actions.value["explicit_cache_control"]
      # host_header_override - (optional) is a type of string
      host_header_override = actions.value["host_header_override"]
      # ip_geolocation - (optional) is a type of string
      ip_geolocation = actions.value["ip_geolocation"]
      # mirage - (optional) is a type of string
      mirage = actions.value["mirage"]
      # opportunistic_encryption - (optional) is a type of string
      opportunistic_encryption = actions.value["opportunistic_encryption"]
      # origin_error_page_pass_thru - (optional) is a type of string
      origin_error_page_pass_thru = actions.value["origin_error_page_pass_thru"]
      # polish - (optional) is a type of string
      polish = actions.value["polish"]
      # resolve_override - (optional) is a type of string
      resolve_override = actions.value["resolve_override"]
      # respect_strong_etag - (optional) is a type of string
      respect_strong_etag = actions.value["respect_strong_etag"]
      # response_buffering - (optional) is a type of string
      response_buffering = actions.value["response_buffering"]
      # rocket_loader - (optional) is a type of string
      rocket_loader = actions.value["rocket_loader"]
      # security_level - (optional) is a type of string
      security_level = actions.value["security_level"]
      # server_side_exclude - (optional) is a type of string
      server_side_exclude = actions.value["server_side_exclude"]
      # sort_query_string_for_cache - (optional) is a type of string
      sort_query_string_for_cache = actions.value["sort_query_string_for_cache"]
      # ssl - (optional) is a type of string
      ssl = actions.value["ssl"]
      # true_client_ip_header - (optional) is a type of string
      true_client_ip_header = actions.value["true_client_ip_header"]
      # waf - (optional) is a type of string
      waf = actions.value["waf"]

      dynamic "cache_key_fields" {
        for_each = actions.value.cache_key_fields
        content {

          dynamic "cookie" {
            for_each = cache_key_fields.value.cookie
            content {
              # check_presence - (optional) is a type of set of string
              check_presence = cookie.value["check_presence"]
              # include - (optional) is a type of set of string
              include = cookie.value["include"]
            }
          }

          dynamic "header" {
            for_each = cache_key_fields.value.header
            content {
              # check_presence - (optional) is a type of set of string
              check_presence = header.value["check_presence"]
              # exclude - (optional) is a type of set of string
              exclude = header.value["exclude"]
              # include - (optional) is a type of set of string
              include = header.value["include"]
            }
          }

          dynamic "host" {
            for_each = cache_key_fields.value.host
            content {
              # resolved - (optional) is a type of bool
              resolved = host.value["resolved"]
            }
          }

          dynamic "query_string" {
            for_each = cache_key_fields.value.query_string
            content {
              # exclude - (optional) is a type of set of string
              exclude = query_string.value["exclude"]
              # ignore - (optional) is a type of bool
              ignore = query_string.value["ignore"]
              # include - (optional) is a type of set of string
              include = query_string.value["include"]
            }
          }

          dynamic "user" {
            for_each = cache_key_fields.value.user
            content {
              # device_type - (optional) is a type of bool
              device_type = user.value["device_type"]
              # geo - (optional) is a type of bool
              geo = user.value["geo"]
              # lang - (optional) is a type of bool
              lang = user.value["lang"]
            }
          }

        }
      }

      dynamic "cache_ttl_by_status" {
        for_each = actions.value.cache_ttl_by_status
        content {
          # codes - (required) is a type of string
          codes = cache_ttl_by_status.value["codes"]
          # ttl - (required) is a type of number
          ttl = cache_ttl_by_status.value["ttl"]
        }
      }

      dynamic "forwarding_url" {
        for_each = actions.value.forwarding_url
        content {
          # status_code - (required) is a type of number
          status_code = forwarding_url.value["status_code"]
          # url - (required) is a type of string
          url = forwarding_url.value["url"]
        }
      }

      dynamic "minify" {
        for_each = actions.value.minify
        content {
          # css - (required) is a type of string
          css = minify.value["css"]
          # html - (required) is a type of string
          html = minify.value["html"]
          # js - (required) is a type of string
          js = minify.value["js"]
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
  value       = cloudflare_page_rule.this.id
}

output "this" {
  value = cloudflare_page_rule.this
}
```

[top](#index)