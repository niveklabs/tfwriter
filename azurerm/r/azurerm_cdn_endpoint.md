# azurerm_cdn_endpoint

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_cdn_endpoint" {
  source = "./modules/azurerm/r/azurerm_cdn_endpoint"

  # content_types_to_compress - (optional) is a type of set of string
  content_types_to_compress = []
  # is_compression_enabled - (optional) is a type of bool
  is_compression_enabled = null
  # is_http_allowed - (optional) is a type of bool
  is_http_allowed = null
  # is_https_allowed - (optional) is a type of bool
  is_https_allowed = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # optimization_type - (optional) is a type of string
  optimization_type = null
  # origin_host_header - (optional) is a type of string
  origin_host_header = null
  # origin_path - (optional) is a type of string
  origin_path = null
  # probe_path - (optional) is a type of string
  probe_path = null
  # profile_name - (required) is a type of string
  profile_name = null
  # querystring_caching_behaviour - (optional) is a type of string
  querystring_caching_behaviour = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  delivery_rule = [{
    cache_expiration_action = [{
      behavior = null
      duration = null
    }]
    cache_key_query_string_action = [{
      behavior   = null
      parameters = null
    }]
    cookies_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      selector         = null
      transforms       = []
    }]
    device_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
    }]
    http_version_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
    }]
    modify_request_header_action = [{
      action = null
      name   = null
      value  = null
    }]
    modify_response_header_action = [{
      action = null
      name   = null
      value  = null
    }]
    name  = null
    order = null
    post_arg_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      selector         = null
      transforms       = []
    }]
    query_string_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      transforms       = []
    }]
    remote_address_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
    }]
    request_body_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      transforms       = []
    }]
    request_header_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      selector         = null
      transforms       = []
    }]
    request_method_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
    }]
    request_scheme_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
    }]
    request_uri_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      transforms       = []
    }]
    url_file_extension_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      transforms       = []
    }]
    url_file_name_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      transforms       = []
    }]
    url_path_condition = [{
      match_values     = []
      negate_condition = null
      operator         = null
      transforms       = []
    }]
    url_redirect_action = [{
      fragment      = null
      hostname      = null
      path          = null
      protocol      = null
      query_string  = null
      redirect_type = null
    }]
    url_rewrite_action = [{
      destination             = null
      preserve_unmatched_path = null
      source_pattern          = null
    }]
  }]

  geo_filter = [{
    action        = null
    country_codes = []
    relative_path = null
  }]

  global_delivery_rule = [{
    cache_expiration_action = [{
      behavior = null
      duration = null
    }]
    cache_key_query_string_action = [{
      behavior   = null
      parameters = null
    }]
    modify_request_header_action = [{
      action = null
      name   = null
      value  = null
    }]
    modify_response_header_action = [{
      action = null
      name   = null
      value  = null
    }]
    url_redirect_action = [{
      fragment      = null
      hostname      = null
      path          = null
      protocol      = null
      query_string  = null
      redirect_type = null
    }]
    url_rewrite_action = [{
      destination             = null
      preserve_unmatched_path = null
      source_pattern          = null
    }]
  }]

  origin = [{
    host_name  = null
    http_port  = null
    https_port = null
    name       = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "content_types_to_compress" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "is_compression_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_http_allowed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_https_allowed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "optimization_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin_host_header" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "probe_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_name" {
  description = "(required)"
  type        = string
}

variable "querystring_caching_behaviour" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "delivery_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cache_expiration_action = list(object(
        {
          behavior = string
          duration = string
        }
      ))
      cache_key_query_string_action = list(object(
        {
          behavior   = string
          parameters = string
        }
      ))
      cookies_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          selector         = string
          transforms       = list(string)
        }
      ))
      device_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
        }
      ))
      http_version_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
        }
      ))
      modify_request_header_action = list(object(
        {
          action = string
          name   = string
          value  = string
        }
      ))
      modify_response_header_action = list(object(
        {
          action = string
          name   = string
          value  = string
        }
      ))
      name  = string
      order = number
      post_arg_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          selector         = string
          transforms       = list(string)
        }
      ))
      query_string_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          transforms       = list(string)
        }
      ))
      remote_address_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
        }
      ))
      request_body_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          transforms       = list(string)
        }
      ))
      request_header_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          selector         = string
          transforms       = list(string)
        }
      ))
      request_method_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
        }
      ))
      request_scheme_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
        }
      ))
      request_uri_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          transforms       = list(string)
        }
      ))
      url_file_extension_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          transforms       = list(string)
        }
      ))
      url_file_name_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          transforms       = list(string)
        }
      ))
      url_path_condition = list(object(
        {
          match_values     = set(string)
          negate_condition = bool
          operator         = string
          transforms       = list(string)
        }
      ))
      url_redirect_action = list(object(
        {
          fragment      = string
          hostname      = string
          path          = string
          protocol      = string
          query_string  = string
          redirect_type = string
        }
      ))
      url_rewrite_action = list(object(
        {
          destination             = string
          preserve_unmatched_path = bool
          source_pattern          = string
        }
      ))
    }
  ))
  default = []
}

variable "geo_filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action        = string
      country_codes = list(string)
      relative_path = string
    }
  ))
  default = []
}

variable "global_delivery_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cache_expiration_action = list(object(
        {
          behavior = string
          duration = string
        }
      ))
      cache_key_query_string_action = list(object(
        {
          behavior   = string
          parameters = string
        }
      ))
      modify_request_header_action = list(object(
        {
          action = string
          name   = string
          value  = string
        }
      ))
      modify_response_header_action = list(object(
        {
          action = string
          name   = string
          value  = string
        }
      ))
      url_redirect_action = list(object(
        {
          fragment      = string
          hostname      = string
          path          = string
          protocol      = string
          query_string  = string
          redirect_type = string
        }
      ))
      url_rewrite_action = list(object(
        {
          destination             = string
          preserve_unmatched_path = bool
          source_pattern          = string
        }
      ))
    }
  ))
  default = []
}

variable "origin" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      host_name  = string
      http_port  = number
      https_port = number
      name       = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_cdn_endpoint" "this" {
  content_types_to_compress     = var.content_types_to_compress
  is_compression_enabled        = var.is_compression_enabled
  is_http_allowed               = var.is_http_allowed
  is_https_allowed              = var.is_https_allowed
  location                      = var.location
  name                          = var.name
  optimization_type             = var.optimization_type
  origin_host_header            = var.origin_host_header
  origin_path                   = var.origin_path
  probe_path                    = var.probe_path
  profile_name                  = var.profile_name
  querystring_caching_behaviour = var.querystring_caching_behaviour
  resource_group_name           = var.resource_group_name
  tags                          = var.tags

  dynamic "delivery_rule" {
    for_each = var.delivery_rule
    content {
      name  = delivery_rule.value["name"]
      order = delivery_rule.value["order"]

      dynamic "cache_expiration_action" {
        for_each = delivery_rule.value.cache_expiration_action
        content {
          behavior = cache_expiration_action.value["behavior"]
          duration = cache_expiration_action.value["duration"]
        }
      }

      dynamic "cache_key_query_string_action" {
        for_each = delivery_rule.value.cache_key_query_string_action
        content {
          behavior   = cache_key_query_string_action.value["behavior"]
          parameters = cache_key_query_string_action.value["parameters"]
        }
      }

      dynamic "cookies_condition" {
        for_each = delivery_rule.value.cookies_condition
        content {
          match_values     = cookies_condition.value["match_values"]
          negate_condition = cookies_condition.value["negate_condition"]
          operator         = cookies_condition.value["operator"]
          selector         = cookies_condition.value["selector"]
          transforms       = cookies_condition.value["transforms"]
        }
      }

      dynamic "device_condition" {
        for_each = delivery_rule.value.device_condition
        content {
          match_values     = device_condition.value["match_values"]
          negate_condition = device_condition.value["negate_condition"]
          operator         = device_condition.value["operator"]
        }
      }

      dynamic "http_version_condition" {
        for_each = delivery_rule.value.http_version_condition
        content {
          match_values     = http_version_condition.value["match_values"]
          negate_condition = http_version_condition.value["negate_condition"]
          operator         = http_version_condition.value["operator"]
        }
      }

      dynamic "modify_request_header_action" {
        for_each = delivery_rule.value.modify_request_header_action
        content {
          action = modify_request_header_action.value["action"]
          name   = modify_request_header_action.value["name"]
          value  = modify_request_header_action.value["value"]
        }
      }

      dynamic "modify_response_header_action" {
        for_each = delivery_rule.value.modify_response_header_action
        content {
          action = modify_response_header_action.value["action"]
          name   = modify_response_header_action.value["name"]
          value  = modify_response_header_action.value["value"]
        }
      }

      dynamic "post_arg_condition" {
        for_each = delivery_rule.value.post_arg_condition
        content {
          match_values     = post_arg_condition.value["match_values"]
          negate_condition = post_arg_condition.value["negate_condition"]
          operator         = post_arg_condition.value["operator"]
          selector         = post_arg_condition.value["selector"]
          transforms       = post_arg_condition.value["transforms"]
        }
      }

      dynamic "query_string_condition" {
        for_each = delivery_rule.value.query_string_condition
        content {
          match_values     = query_string_condition.value["match_values"]
          negate_condition = query_string_condition.value["negate_condition"]
          operator         = query_string_condition.value["operator"]
          transforms       = query_string_condition.value["transforms"]
        }
      }

      dynamic "remote_address_condition" {
        for_each = delivery_rule.value.remote_address_condition
        content {
          match_values     = remote_address_condition.value["match_values"]
          negate_condition = remote_address_condition.value["negate_condition"]
          operator         = remote_address_condition.value["operator"]
        }
      }

      dynamic "request_body_condition" {
        for_each = delivery_rule.value.request_body_condition
        content {
          match_values     = request_body_condition.value["match_values"]
          negate_condition = request_body_condition.value["negate_condition"]
          operator         = request_body_condition.value["operator"]
          transforms       = request_body_condition.value["transforms"]
        }
      }

      dynamic "request_header_condition" {
        for_each = delivery_rule.value.request_header_condition
        content {
          match_values     = request_header_condition.value["match_values"]
          negate_condition = request_header_condition.value["negate_condition"]
          operator         = request_header_condition.value["operator"]
          selector         = request_header_condition.value["selector"]
          transforms       = request_header_condition.value["transforms"]
        }
      }

      dynamic "request_method_condition" {
        for_each = delivery_rule.value.request_method_condition
        content {
          match_values     = request_method_condition.value["match_values"]
          negate_condition = request_method_condition.value["negate_condition"]
          operator         = request_method_condition.value["operator"]
        }
      }

      dynamic "request_scheme_condition" {
        for_each = delivery_rule.value.request_scheme_condition
        content {
          match_values     = request_scheme_condition.value["match_values"]
          negate_condition = request_scheme_condition.value["negate_condition"]
          operator         = request_scheme_condition.value["operator"]
        }
      }

      dynamic "request_uri_condition" {
        for_each = delivery_rule.value.request_uri_condition
        content {
          match_values     = request_uri_condition.value["match_values"]
          negate_condition = request_uri_condition.value["negate_condition"]
          operator         = request_uri_condition.value["operator"]
          transforms       = request_uri_condition.value["transforms"]
        }
      }

      dynamic "url_file_extension_condition" {
        for_each = delivery_rule.value.url_file_extension_condition
        content {
          match_values     = url_file_extension_condition.value["match_values"]
          negate_condition = url_file_extension_condition.value["negate_condition"]
          operator         = url_file_extension_condition.value["operator"]
          transforms       = url_file_extension_condition.value["transforms"]
        }
      }

      dynamic "url_file_name_condition" {
        for_each = delivery_rule.value.url_file_name_condition
        content {
          match_values     = url_file_name_condition.value["match_values"]
          negate_condition = url_file_name_condition.value["negate_condition"]
          operator         = url_file_name_condition.value["operator"]
          transforms       = url_file_name_condition.value["transforms"]
        }
      }

      dynamic "url_path_condition" {
        for_each = delivery_rule.value.url_path_condition
        content {
          match_values     = url_path_condition.value["match_values"]
          negate_condition = url_path_condition.value["negate_condition"]
          operator         = url_path_condition.value["operator"]
          transforms       = url_path_condition.value["transforms"]
        }
      }

      dynamic "url_redirect_action" {
        for_each = delivery_rule.value.url_redirect_action
        content {
          fragment      = url_redirect_action.value["fragment"]
          hostname      = url_redirect_action.value["hostname"]
          path          = url_redirect_action.value["path"]
          protocol      = url_redirect_action.value["protocol"]
          query_string  = url_redirect_action.value["query_string"]
          redirect_type = url_redirect_action.value["redirect_type"]
        }
      }

      dynamic "url_rewrite_action" {
        for_each = delivery_rule.value.url_rewrite_action
        content {
          destination             = url_rewrite_action.value["destination"]
          preserve_unmatched_path = url_rewrite_action.value["preserve_unmatched_path"]
          source_pattern          = url_rewrite_action.value["source_pattern"]
        }
      }

    }
  }

  dynamic "geo_filter" {
    for_each = var.geo_filter
    content {
      action        = geo_filter.value["action"]
      country_codes = geo_filter.value["country_codes"]
      relative_path = geo_filter.value["relative_path"]
    }
  }

  dynamic "global_delivery_rule" {
    for_each = var.global_delivery_rule
    content {

      dynamic "cache_expiration_action" {
        for_each = global_delivery_rule.value.cache_expiration_action
        content {
          behavior = cache_expiration_action.value["behavior"]
          duration = cache_expiration_action.value["duration"]
        }
      }

      dynamic "cache_key_query_string_action" {
        for_each = global_delivery_rule.value.cache_key_query_string_action
        content {
          behavior   = cache_key_query_string_action.value["behavior"]
          parameters = cache_key_query_string_action.value["parameters"]
        }
      }

      dynamic "modify_request_header_action" {
        for_each = global_delivery_rule.value.modify_request_header_action
        content {
          action = modify_request_header_action.value["action"]
          name   = modify_request_header_action.value["name"]
          value  = modify_request_header_action.value["value"]
        }
      }

      dynamic "modify_response_header_action" {
        for_each = global_delivery_rule.value.modify_response_header_action
        content {
          action = modify_response_header_action.value["action"]
          name   = modify_response_header_action.value["name"]
          value  = modify_response_header_action.value["value"]
        }
      }

      dynamic "url_redirect_action" {
        for_each = global_delivery_rule.value.url_redirect_action
        content {
          fragment      = url_redirect_action.value["fragment"]
          hostname      = url_redirect_action.value["hostname"]
          path          = url_redirect_action.value["path"]
          protocol      = url_redirect_action.value["protocol"]
          query_string  = url_redirect_action.value["query_string"]
          redirect_type = url_redirect_action.value["redirect_type"]
        }
      }

      dynamic "url_rewrite_action" {
        for_each = global_delivery_rule.value.url_rewrite_action
        content {
          destination             = url_rewrite_action.value["destination"]
          preserve_unmatched_path = url_rewrite_action.value["preserve_unmatched_path"]
          source_pattern          = url_rewrite_action.value["source_pattern"]
        }
      }

    }
  }

  dynamic "origin" {
    for_each = var.origin
    content {
      host_name  = origin.value["host_name"]
      http_port  = origin.value["http_port"]
      https_port = origin.value["https_port"]
      name       = origin.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "content_types_to_compress" {
  description = "returns a set of string"
  value       = azurerm_cdn_endpoint.this.content_types_to_compress
}

output "host_name" {
  description = "returns a string"
  value       = azurerm_cdn_endpoint.this.host_name
}

output "id" {
  description = "returns a string"
  value       = azurerm_cdn_endpoint.this.id
}

output "origin_path" {
  description = "returns a string"
  value       = azurerm_cdn_endpoint.this.origin_path
}

output "probe_path" {
  description = "returns a string"
  value       = azurerm_cdn_endpoint.this.probe_path
}

output "this" {
  value = azurerm_cdn_endpoint.this
}
```

[top](#index)