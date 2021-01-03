# cloudflare_zone_settings_override

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
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_zone_settings_override" {
  source = "./modules/cloudflare/r/cloudflare_zone_settings_override"

  # zone_id - (required) is a type of string
  zone_id = null

  settings = [{
    always_online            = null
    always_use_https         = null
    automatic_https_rewrites = null
    brotli                   = null
    browser_cache_ttl        = null
    browser_check            = null
    cache_level              = null
    challenge_ttl            = null
    cname_flattening         = null
    development_mode         = null
    email_obfuscation        = null
    h2_prioritization        = null
    hotlink_protection       = null
    http2                    = null
    http3                    = null
    image_resizing           = null
    ip_geolocation           = null
    ipv6                     = null
    max_upload               = null
    min_tls_version          = null
    minify = [{
      css  = null
      html = null
      js   = null
    }]
    mirage = null
    mobile_redirect = [{
      mobile_subdomain = null
      status           = null
      strip_uri        = null
    }]
    opportunistic_encryption    = null
    opportunistic_onion         = null
    origin_error_page_pass_thru = null
    polish                      = null
    prefetch_preload            = null
    privacy_pass                = null
    pseudo_ipv4                 = null
    response_buffering          = null
    rocket_loader               = null
    security_header = [{
      enabled            = null
      include_subdomains = null
      max_age            = null
      nosniff            = null
      preload            = null
    }]
    security_level              = null
    server_side_exclude         = null
    sort_query_string_for_cache = null
    ssl                         = null
    tls_1_2_only                = null
    tls_1_3                     = null
    tls_client_auth             = null
    true_client_ip_header       = null
    universal_ssl               = null
    waf                         = null
    webp                        = null
    websockets                  = null
    zero_rtt                    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      always_online            = string
      always_use_https         = string
      automatic_https_rewrites = string
      brotli                   = string
      browser_cache_ttl        = number
      browser_check            = string
      cache_level              = string
      challenge_ttl            = number
      cname_flattening         = string
      development_mode         = string
      email_obfuscation        = string
      h2_prioritization        = string
      hotlink_protection       = string
      http2                    = string
      http3                    = string
      image_resizing           = string
      ip_geolocation           = string
      ipv6                     = string
      max_upload               = number
      min_tls_version          = string
      minify = list(object(
        {
          css  = string
          html = string
          js   = string
        }
      ))
      mirage = string
      mobile_redirect = list(object(
        {
          mobile_subdomain = string
          status           = string
          strip_uri        = bool
        }
      ))
      opportunistic_encryption    = string
      opportunistic_onion         = string
      origin_error_page_pass_thru = string
      polish                      = string
      prefetch_preload            = string
      privacy_pass                = string
      pseudo_ipv4                 = string
      response_buffering          = string
      rocket_loader               = string
      security_header = list(object(
        {
          enabled            = bool
          include_subdomains = bool
          max_age            = number
          nosniff            = bool
          preload            = bool
        }
      ))
      security_level              = string
      server_side_exclude         = string
      sort_query_string_for_cache = string
      ssl                         = string
      tls_1_2_only                = string
      tls_1_3                     = string
      tls_client_auth             = string
      true_client_ip_header       = string
      universal_ssl               = string
      waf                         = string
      webp                        = string
      websockets                  = string
      zero_rtt                    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_zone_settings_override" "this" {
  zone_id = var.zone_id

  dynamic "settings" {
    for_each = var.settings
    content {
      always_online               = settings.value["always_online"]
      always_use_https            = settings.value["always_use_https"]
      automatic_https_rewrites    = settings.value["automatic_https_rewrites"]
      brotli                      = settings.value["brotli"]
      browser_cache_ttl           = settings.value["browser_cache_ttl"]
      browser_check               = settings.value["browser_check"]
      cache_level                 = settings.value["cache_level"]
      challenge_ttl               = settings.value["challenge_ttl"]
      cname_flattening            = settings.value["cname_flattening"]
      development_mode            = settings.value["development_mode"]
      email_obfuscation           = settings.value["email_obfuscation"]
      h2_prioritization           = settings.value["h2_prioritization"]
      hotlink_protection          = settings.value["hotlink_protection"]
      http2                       = settings.value["http2"]
      http3                       = settings.value["http3"]
      image_resizing              = settings.value["image_resizing"]
      ip_geolocation              = settings.value["ip_geolocation"]
      ipv6                        = settings.value["ipv6"]
      max_upload                  = settings.value["max_upload"]
      min_tls_version             = settings.value["min_tls_version"]
      mirage                      = settings.value["mirage"]
      opportunistic_encryption    = settings.value["opportunistic_encryption"]
      opportunistic_onion         = settings.value["opportunistic_onion"]
      origin_error_page_pass_thru = settings.value["origin_error_page_pass_thru"]
      polish                      = settings.value["polish"]
      prefetch_preload            = settings.value["prefetch_preload"]
      privacy_pass                = settings.value["privacy_pass"]
      pseudo_ipv4                 = settings.value["pseudo_ipv4"]
      response_buffering          = settings.value["response_buffering"]
      rocket_loader               = settings.value["rocket_loader"]
      security_level              = settings.value["security_level"]
      server_side_exclude         = settings.value["server_side_exclude"]
      sort_query_string_for_cache = settings.value["sort_query_string_for_cache"]
      ssl                         = settings.value["ssl"]
      tls_1_2_only                = settings.value["tls_1_2_only"]
      tls_1_3                     = settings.value["tls_1_3"]
      tls_client_auth             = settings.value["tls_client_auth"]
      true_client_ip_header       = settings.value["true_client_ip_header"]
      universal_ssl               = settings.value["universal_ssl"]
      waf                         = settings.value["waf"]
      webp                        = settings.value["webp"]
      websockets                  = settings.value["websockets"]
      zero_rtt                    = settings.value["zero_rtt"]

      dynamic "minify" {
        for_each = settings.value.minify
        content {
          css  = minify.value["css"]
          html = minify.value["html"]
          js   = minify.value["js"]
        }
      }

      dynamic "mobile_redirect" {
        for_each = settings.value.mobile_redirect
        content {
          mobile_subdomain = mobile_redirect.value["mobile_subdomain"]
          status           = mobile_redirect.value["status"]
          strip_uri        = mobile_redirect.value["strip_uri"]
        }
      }

      dynamic "security_header" {
        for_each = settings.value.security_header
        content {
          enabled            = security_header.value["enabled"]
          include_subdomains = security_header.value["include_subdomains"]
          max_age            = security_header.value["max_age"]
          nosniff            = security_header.value["nosniff"]
          preload            = security_header.value["preload"]
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
  value       = cloudflare_zone_settings_override.this.id
}

output "initial_settings" {
  description = "returns a list of object"
  value       = cloudflare_zone_settings_override.this.initial_settings
}

output "initial_settings_read_at" {
  description = "returns a string"
  value       = cloudflare_zone_settings_override.this.initial_settings_read_at
}

output "readonly_settings" {
  description = "returns a list of string"
  value       = cloudflare_zone_settings_override.this.readonly_settings
}

output "zone_status" {
  description = "returns a string"
  value       = cloudflare_zone_settings_override.this.zone_status
}

output "zone_type" {
  description = "returns a string"
  value       = cloudflare_zone_settings_override.this.zone_type
}

output "this" {
  value = cloudflare_zone_settings_override.this
}
```

[top](#index)