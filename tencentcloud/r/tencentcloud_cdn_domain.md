# tencentcloud_cdn_domain

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cdn_domain" {
  source = "./modules/tencentcloud/r/tencentcloud_cdn_domain"

  # area - (optional) is a type of string
  area = null
  # domain - (required) is a type of string
  domain = null
  # full_url_cache - (optional) is a type of bool
  full_url_cache = null
  # project_id - (optional) is a type of number
  project_id = null
  # range_origin_switch - (optional) is a type of string
  range_origin_switch = null
  # service_type - (required) is a type of string
  service_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  https_config = [{
    client_certificate_config = [{
      certificate_content = null
      certificate_name    = null
      deploy_time         = null
      expire_time         = null
    }]
    force_redirect = [{
      redirect_status_code = null
      redirect_type        = null
      switch               = null
    }]
    http2_switch         = null
    https_switch         = null
    ocsp_stapling_switch = null
    server_certificate_config = [{
      certificate_content = null
      certificate_id      = null
      certificate_name    = null
      deploy_time         = null
      expire_time         = null
      message             = null
      private_key         = null
    }]
    spdy_switch   = null
    verify_client = null
  }]

  origin = [{
    backup_origin_list   = []
    backup_origin_type   = null
    backup_server_name   = null
    cos_private_access   = null
    origin_list          = []
    origin_pull_protocol = null
    origin_type          = null
    server_name          = null
  }]

  request_header = [{
    header_rules = [{
      header_mode  = null
      header_name  = null
      header_value = null
      rule_paths   = []
      rule_type    = null
    }]
    switch = null
  }]

  rule_cache = [{
    cache_time           = null
    compare_max_age      = null
    follow_origin_switch = null
    ignore_cache_control = null
    ignore_set_cookie    = null
    no_cache_switch      = null
    re_validate          = null
    rule_paths           = []
    rule_type            = null
    switch               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "area" {
  description = "(optional) - Domain name acceleration region. `mainland`: acceleration inside mainland China, `overseas`: acceleration outside mainland China, `global`: global acceleration. Overseas acceleration service must be enabled to use overseas acceleration and global acceleration."
  type        = string
  default     = null
}

variable "domain" {
  description = "(required) - Name of the acceleration domain."
  type        = string
}

variable "full_url_cache" {
  description = "(optional) - Whether to enable full-path cache. Default value is `true`."
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(optional) - The project CDN belongs to, default to 0."
  type        = number
  default     = null
}

variable "range_origin_switch" {
  description = "(optional) - Sharding back to source configuration switch. Valid values are `on` and `off`. Default value is `on`."
  type        = string
  default     = null
}

variable "service_type" {
  description = "(required) - Acceleration domain name service type. `web`: static acceleration, `download`: download acceleration, `media`: streaming media VOD acceleration."
  type        = string
}

variable "tags" {
  description = "(optional) - Tags of cdn domain."
  type        = map(string)
  default     = null
}

variable "https_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_certificate_config = list(object(
        {
          certificate_content = string
          certificate_name    = string
          deploy_time         = string
          expire_time         = string
        }
      ))
      force_redirect = list(object(
        {
          redirect_status_code = number
          redirect_type        = string
          switch               = string
        }
      ))
      http2_switch         = string
      https_switch         = string
      ocsp_stapling_switch = string
      server_certificate_config = list(object(
        {
          certificate_content = string
          certificate_id      = string
          certificate_name    = string
          deploy_time         = string
          expire_time         = string
          message             = string
          private_key         = string
        }
      ))
      spdy_switch   = string
      verify_client = string
    }
  ))
  default = []
}

variable "origin" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      backup_origin_list   = list(string)
      backup_origin_type   = string
      backup_server_name   = string
      cos_private_access   = string
      origin_list          = list(string)
      origin_pull_protocol = string
      origin_type          = string
      server_name          = string
    }
  ))
}

variable "request_header" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      header_rules = list(object(
        {
          header_mode  = string
          header_name  = string
          header_value = string
          rule_paths   = list(string)
          rule_type    = string
        }
      ))
      switch = string
    }
  ))
  default = []
}

variable "rule_cache" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cache_time           = number
      compare_max_age      = string
      follow_origin_switch = string
      ignore_cache_control = string
      ignore_set_cookie    = string
      no_cache_switch      = string
      re_validate          = string
      rule_paths           = list(string)
      rule_type            = string
      switch               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cdn_domain" "this" {
  area                = var.area
  domain              = var.domain
  full_url_cache      = var.full_url_cache
  project_id          = var.project_id
  range_origin_switch = var.range_origin_switch
  service_type        = var.service_type
  tags                = var.tags

  dynamic "https_config" {
    for_each = var.https_config
    content {
      http2_switch         = https_config.value["http2_switch"]
      https_switch         = https_config.value["https_switch"]
      ocsp_stapling_switch = https_config.value["ocsp_stapling_switch"]
      spdy_switch          = https_config.value["spdy_switch"]
      verify_client        = https_config.value["verify_client"]

      dynamic "client_certificate_config" {
        for_each = https_config.value.client_certificate_config
        content {
          certificate_content = client_certificate_config.value["certificate_content"]
        }
      }

      dynamic "force_redirect" {
        for_each = https_config.value.force_redirect
        content {
          redirect_status_code = force_redirect.value["redirect_status_code"]
          redirect_type        = force_redirect.value["redirect_type"]
          switch               = force_redirect.value["switch"]
        }
      }

      dynamic "server_certificate_config" {
        for_each = https_config.value.server_certificate_config
        content {
          certificate_content = server_certificate_config.value["certificate_content"]
          certificate_id      = server_certificate_config.value["certificate_id"]
          message             = server_certificate_config.value["message"]
          private_key         = server_certificate_config.value["private_key"]
        }
      }

    }
  }

  dynamic "origin" {
    for_each = var.origin
    content {
      backup_origin_list   = origin.value["backup_origin_list"]
      backup_origin_type   = origin.value["backup_origin_type"]
      backup_server_name   = origin.value["backup_server_name"]
      cos_private_access   = origin.value["cos_private_access"]
      origin_list          = origin.value["origin_list"]
      origin_pull_protocol = origin.value["origin_pull_protocol"]
      origin_type          = origin.value["origin_type"]
      server_name          = origin.value["server_name"]
    }
  }

  dynamic "request_header" {
    for_each = var.request_header
    content {
      switch = request_header.value["switch"]

      dynamic "header_rules" {
        for_each = request_header.value.header_rules
        content {
          header_mode  = header_rules.value["header_mode"]
          header_name  = header_rules.value["header_name"]
          header_value = header_rules.value["header_value"]
          rule_paths   = header_rules.value["rule_paths"]
          rule_type    = header_rules.value["rule_type"]
        }
      }

    }
  }

  dynamic "rule_cache" {
    for_each = var.rule_cache
    content {
      cache_time           = rule_cache.value["cache_time"]
      compare_max_age      = rule_cache.value["compare_max_age"]
      follow_origin_switch = rule_cache.value["follow_origin_switch"]
      ignore_cache_control = rule_cache.value["ignore_cache_control"]
      ignore_set_cookie    = rule_cache.value["ignore_set_cookie"]
      no_cache_switch      = rule_cache.value["no_cache_switch"]
      re_validate          = rule_cache.value["re_validate"]
      rule_paths           = rule_cache.value["rule_paths"]
      rule_type            = rule_cache.value["rule_type"]
      switch               = rule_cache.value["switch"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cname" {
  description = "returns a string"
  value       = tencentcloud_cdn_domain.this.cname
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cdn_domain.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cdn_domain.this.id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_cdn_domain.this.status
}

output "this" {
  value = tencentcloud_cdn_domain.this
}
```

[top](#index)