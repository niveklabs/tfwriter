# alicloud_cdn_domain

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cdn_domain" {
  source = "./modules/alicloud/r/alicloud_cdn_domain"

  # block_ips - (optional) is a type of set of string
  block_ips = []
  # cdn_type - (required) is a type of string
  cdn_type = null
  # domain_name - (required) is a type of string
  domain_name = null
  # optimize_enable - (optional) is a type of string
  optimize_enable = null
  # page_compress_enable - (optional) is a type of string
  page_compress_enable = null
  # range_enable - (optional) is a type of string
  range_enable = null
  # scope - (optional) is a type of string
  scope = null
  # source_port - (optional) is a type of number
  source_port = null
  # source_type - (optional) is a type of string
  source_type = null
  # sources - (optional) is a type of set of string
  sources = []
  # video_seek_enable - (optional) is a type of string
  video_seek_enable = null

  auth_config = [{
    auth_type  = null
    master_key = null
    slave_key  = null
    timeout    = null
  }]

  cache_config = [{
    cache_content = null
    cache_id      = null
    cache_type    = null
    ttl           = null
    weight        = null
  }]

  certificate_config = [{
    private_key               = null
    server_certificate        = null
    server_certificate_status = null
  }]

  http_header_config = [{
    header_id    = null
    header_key   = null
    header_value = null
  }]

  page_404_config = [{
    custom_page_url = null
    error_code      = null
    page_type       = null
  }]

  parameter_filter_config = [{
    enable        = null
    hash_key_args = []
  }]

  refer_config = [{
    allow_empty = null
    refer_list  = []
    refer_type  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cdn_type" {
  description = "(required)"
  type        = string
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "optimize_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "page_compress_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "range_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sources" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "video_seek_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      auth_type  = string
      master_key = string
      slave_key  = string
      timeout    = number
    }
  ))
  default = []
}

variable "cache_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cache_content = string
      cache_id      = string
      cache_type    = string
      ttl           = number
      weight        = number
    }
  ))
  default = []
}

variable "certificate_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      private_key               = string
      server_certificate        = string
      server_certificate_status = string
    }
  ))
  default = []
}

variable "http_header_config" {
  description = "nested block: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      header_id    = string
      header_key   = string
      header_value = string
    }
  ))
  default = []
}

variable "page_404_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      custom_page_url = string
      error_code      = string
      page_type       = string
    }
  ))
  default = []
}

variable "parameter_filter_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      enable        = string
      hash_key_args = list(string)
    }
  ))
  default = []
}

variable "refer_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      allow_empty = string
      refer_list  = list(string)
      refer_type  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cdn_domain" "this" {
  # block_ips - (optional) is a type of set of string
  block_ips = var.block_ips
  # cdn_type - (required) is a type of string
  cdn_type = var.cdn_type
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
  # optimize_enable - (optional) is a type of string
  optimize_enable = var.optimize_enable
  # page_compress_enable - (optional) is a type of string
  page_compress_enable = var.page_compress_enable
  # range_enable - (optional) is a type of string
  range_enable = var.range_enable
  # scope - (optional) is a type of string
  scope = var.scope
  # source_port - (optional) is a type of number
  source_port = var.source_port
  # source_type - (optional) is a type of string
  source_type = var.source_type
  # sources - (optional) is a type of set of string
  sources = var.sources
  # video_seek_enable - (optional) is a type of string
  video_seek_enable = var.video_seek_enable

  dynamic "auth_config" {
    for_each = var.auth_config
    content {
      # auth_type - (optional) is a type of string
      auth_type = auth_config.value["auth_type"]
      # master_key - (optional) is a type of string
      master_key = auth_config.value["master_key"]
      # slave_key - (optional) is a type of string
      slave_key = auth_config.value["slave_key"]
      # timeout - (optional) is a type of number
      timeout = auth_config.value["timeout"]
    }
  }

  dynamic "cache_config" {
    for_each = var.cache_config
    content {
      # cache_content - (required) is a type of string
      cache_content = cache_config.value["cache_content"]
      # cache_type - (required) is a type of string
      cache_type = cache_config.value["cache_type"]
      # ttl - (required) is a type of number
      ttl = cache_config.value["ttl"]
      # weight - (optional) is a type of number
      weight = cache_config.value["weight"]
    }
  }

  dynamic "certificate_config" {
    for_each = var.certificate_config
    content {
      # private_key - (optional) is a type of string
      private_key = certificate_config.value["private_key"]
      # server_certificate - (optional) is a type of string
      server_certificate = certificate_config.value["server_certificate"]
      # server_certificate_status - (optional) is a type of string
      server_certificate_status = certificate_config.value["server_certificate_status"]
    }
  }

  dynamic "http_header_config" {
    for_each = var.http_header_config
    content {
      # header_key - (required) is a type of string
      header_key = http_header_config.value["header_key"]
      # header_value - (required) is a type of string
      header_value = http_header_config.value["header_value"]
    }
  }

  dynamic "page_404_config" {
    for_each = var.page_404_config
    content {
      # custom_page_url - (optional) is a type of string
      custom_page_url = page_404_config.value["custom_page_url"]
      # page_type - (optional) is a type of string
      page_type = page_404_config.value["page_type"]
    }
  }

  dynamic "parameter_filter_config" {
    for_each = var.parameter_filter_config
    content {
      # enable - (optional) is a type of string
      enable = parameter_filter_config.value["enable"]
      # hash_key_args - (optional) is a type of list of string
      hash_key_args = parameter_filter_config.value["hash_key_args"]
    }
  }

  dynamic "refer_config" {
    for_each = var.refer_config
    content {
      # allow_empty - (optional) is a type of string
      allow_empty = refer_config.value["allow_empty"]
      # refer_list - (required) is a type of list of string
      refer_list = refer_config.value["refer_list"]
      # refer_type - (optional) is a type of string
      refer_type = refer_config.value["refer_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cdn_domain.this.id
}

output "scope" {
  description = "returns a string"
  value       = alicloud_cdn_domain.this.scope
}

output "this" {
  value = alicloud_cdn_domain.this
}
```

[top](#index)