# aws_cloudfront_distribution

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_cloudfront_distribution" {
  source = "./modules/aws/r/aws_cloudfront_distribution"

  # aliases - (optional) is a type of set of string
  aliases = []
  # comment - (optional) is a type of string
  comment = null
  # default_root_object - (optional) is a type of string
  default_root_object = null
  # enabled - (required) is a type of bool
  enabled = null
  # http_version - (optional) is a type of string
  http_version = null
  # is_ipv6_enabled - (optional) is a type of bool
  is_ipv6_enabled = null
  # price_class - (optional) is a type of string
  price_class = null
  # retain_on_delete - (optional) is a type of bool
  retain_on_delete = null
  # tags - (optional) is a type of map of string
  tags = {}
  # wait_for_deployment - (optional) is a type of bool
  wait_for_deployment = null
  # web_acl_id - (optional) is a type of string
  web_acl_id = null

  custom_error_response = [{
    error_caching_min_ttl = null
    error_code            = null
    response_code         = null
    response_page_path    = null
  }]

  default_cache_behavior = [{
    allowed_methods           = []
    cached_methods            = []
    compress                  = null
    default_ttl               = null
    field_level_encryption_id = null
    forwarded_values = [{
      cookies = [{
        forward           = null
        whitelisted_names = []
      }]
      headers                 = []
      query_string            = null
      query_string_cache_keys = []
    }]
    lambda_function_association = [{
      event_type   = null
      include_body = null
      lambda_arn   = null
    }]
    max_ttl                = null
    min_ttl                = null
    smooth_streaming       = null
    target_origin_id       = null
    trusted_signers        = []
    viewer_protocol_policy = null
  }]

  logging_config = [{
    bucket          = null
    include_cookies = null
    prefix          = null
  }]

  ordered_cache_behavior = [{
    allowed_methods           = []
    cached_methods            = []
    compress                  = null
    default_ttl               = null
    field_level_encryption_id = null
    forwarded_values = [{
      cookies = [{
        forward           = null
        whitelisted_names = []
      }]
      headers                 = []
      query_string            = null
      query_string_cache_keys = []
    }]
    lambda_function_association = [{
      event_type   = null
      include_body = null
      lambda_arn   = null
    }]
    max_ttl                = null
    min_ttl                = null
    path_pattern           = null
    smooth_streaming       = null
    target_origin_id       = null
    trusted_signers        = []
    viewer_protocol_policy = null
  }]

  origin = [{
    custom_header = [{
      name  = null
      value = null
    }]
    custom_origin_config = [{
      http_port                = null
      https_port               = null
      origin_keepalive_timeout = null
      origin_protocol_policy   = null
      origin_read_timeout      = null
      origin_ssl_protocols     = []
    }]
    domain_name = null
    origin_id   = null
    origin_path = null
    s3_origin_config = [{
      origin_access_identity = null
    }]
  }]

  origin_group = [{
    failover_criteria = [{
      status_codes = []
    }]
    member = [{
      origin_id = null
    }]
    origin_id = null
  }]

  restrictions = [{
    geo_restriction = [{
      locations        = []
      restriction_type = null
    }]
  }]

  viewer_certificate = [{
    acm_certificate_arn            = null
    cloudfront_default_certificate = null
    iam_certificate_id             = null
    minimum_protocol_version       = null
    ssl_support_method             = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "aliases" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_root_object" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "http_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_ipv6_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "price_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retain_on_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "wait_for_deployment" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "web_acl_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_error_response" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      error_caching_min_ttl = number
      error_code            = number
      response_code         = number
      response_page_path    = string
    }
  ))
  default = []
}

variable "default_cache_behavior" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      allowed_methods           = set(string)
      cached_methods            = set(string)
      compress                  = bool
      default_ttl               = number
      field_level_encryption_id = string
      forwarded_values = list(object(
        {
          cookies = list(object(
            {
              forward           = string
              whitelisted_names = set(string)
            }
          ))
          headers                 = set(string)
          query_string            = bool
          query_string_cache_keys = list(string)
        }
      ))
      lambda_function_association = set(object(
        {
          event_type   = string
          include_body = bool
          lambda_arn   = string
        }
      ))
      max_ttl                = number
      min_ttl                = number
      smooth_streaming       = bool
      target_origin_id       = string
      trusted_signers        = list(string)
      viewer_protocol_policy = string
    }
  ))
}

variable "logging_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket          = string
      include_cookies = bool
      prefix          = string
    }
  ))
  default = []
}

variable "ordered_cache_behavior" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_methods           = set(string)
      cached_methods            = set(string)
      compress                  = bool
      default_ttl               = number
      field_level_encryption_id = string
      forwarded_values = list(object(
        {
          cookies = list(object(
            {
              forward           = string
              whitelisted_names = set(string)
            }
          ))
          headers                 = set(string)
          query_string            = bool
          query_string_cache_keys = list(string)
        }
      ))
      lambda_function_association = set(object(
        {
          event_type   = string
          include_body = bool
          lambda_arn   = string
        }
      ))
      max_ttl                = number
      min_ttl                = number
      path_pattern           = string
      smooth_streaming       = bool
      target_origin_id       = string
      trusted_signers        = list(string)
      viewer_protocol_policy = string
    }
  ))
  default = []
}

variable "origin" {
  description = "nested mode: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      custom_header = set(object(
        {
          name  = string
          value = string
        }
      ))
      custom_origin_config = list(object(
        {
          http_port                = number
          https_port               = number
          origin_keepalive_timeout = number
          origin_protocol_policy   = string
          origin_read_timeout      = number
          origin_ssl_protocols     = set(string)
        }
      ))
      domain_name = string
      origin_id   = string
      origin_path = string
      s3_origin_config = list(object(
        {
          origin_access_identity = string
        }
      ))
    }
  ))
}

variable "origin_group" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      failover_criteria = list(object(
        {
          status_codes = set(number)
        }
      ))
      member = list(object(
        {
          origin_id = string
        }
      ))
      origin_id = string
    }
  ))
  default = []
}

variable "restrictions" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      geo_restriction = list(object(
        {
          locations        = set(string)
          restriction_type = string
        }
      ))
    }
  ))
}

variable "viewer_certificate" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      acm_certificate_arn            = string
      cloudfront_default_certificate = bool
      iam_certificate_id             = string
      minimum_protocol_version       = string
      ssl_support_method             = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_cloudfront_distribution" "this" {
  aliases             = var.aliases
  comment             = var.comment
  default_root_object = var.default_root_object
  enabled             = var.enabled
  http_version        = var.http_version
  is_ipv6_enabled     = var.is_ipv6_enabled
  price_class         = var.price_class
  retain_on_delete    = var.retain_on_delete
  tags                = var.tags
  wait_for_deployment = var.wait_for_deployment
  web_acl_id          = var.web_acl_id

  dynamic "custom_error_response" {
    for_each = var.custom_error_response
    content {
      error_caching_min_ttl = custom_error_response.value["error_caching_min_ttl"]
      error_code            = custom_error_response.value["error_code"]
      response_code         = custom_error_response.value["response_code"]
      response_page_path    = custom_error_response.value["response_page_path"]
    }
  }

  dynamic "default_cache_behavior" {
    for_each = var.default_cache_behavior
    content {
      allowed_methods           = default_cache_behavior.value["allowed_methods"]
      cached_methods            = default_cache_behavior.value["cached_methods"]
      compress                  = default_cache_behavior.value["compress"]
      default_ttl               = default_cache_behavior.value["default_ttl"]
      field_level_encryption_id = default_cache_behavior.value["field_level_encryption_id"]
      max_ttl                   = default_cache_behavior.value["max_ttl"]
      min_ttl                   = default_cache_behavior.value["min_ttl"]
      smooth_streaming          = default_cache_behavior.value["smooth_streaming"]
      target_origin_id          = default_cache_behavior.value["target_origin_id"]
      trusted_signers           = default_cache_behavior.value["trusted_signers"]
      viewer_protocol_policy    = default_cache_behavior.value["viewer_protocol_policy"]

      dynamic "forwarded_values" {
        for_each = default_cache_behavior.value.forwarded_values
        content {
          headers                 = forwarded_values.value["headers"]
          query_string            = forwarded_values.value["query_string"]
          query_string_cache_keys = forwarded_values.value["query_string_cache_keys"]

          dynamic "cookies" {
            for_each = forwarded_values.value.cookies
            content {
              forward           = cookies.value["forward"]
              whitelisted_names = cookies.value["whitelisted_names"]
            }
          }

        }
      }

      dynamic "lambda_function_association" {
        for_each = default_cache_behavior.value.lambda_function_association
        content {
          event_type   = lambda_function_association.value["event_type"]
          include_body = lambda_function_association.value["include_body"]
          lambda_arn   = lambda_function_association.value["lambda_arn"]
        }
      }

    }
  }

  dynamic "logging_config" {
    for_each = var.logging_config
    content {
      bucket          = logging_config.value["bucket"]
      include_cookies = logging_config.value["include_cookies"]
      prefix          = logging_config.value["prefix"]
    }
  }

  dynamic "ordered_cache_behavior" {
    for_each = var.ordered_cache_behavior
    content {
      allowed_methods           = ordered_cache_behavior.value["allowed_methods"]
      cached_methods            = ordered_cache_behavior.value["cached_methods"]
      compress                  = ordered_cache_behavior.value["compress"]
      default_ttl               = ordered_cache_behavior.value["default_ttl"]
      field_level_encryption_id = ordered_cache_behavior.value["field_level_encryption_id"]
      max_ttl                   = ordered_cache_behavior.value["max_ttl"]
      min_ttl                   = ordered_cache_behavior.value["min_ttl"]
      path_pattern              = ordered_cache_behavior.value["path_pattern"]
      smooth_streaming          = ordered_cache_behavior.value["smooth_streaming"]
      target_origin_id          = ordered_cache_behavior.value["target_origin_id"]
      trusted_signers           = ordered_cache_behavior.value["trusted_signers"]
      viewer_protocol_policy    = ordered_cache_behavior.value["viewer_protocol_policy"]

      dynamic "forwarded_values" {
        for_each = ordered_cache_behavior.value.forwarded_values
        content {
          headers                 = forwarded_values.value["headers"]
          query_string            = forwarded_values.value["query_string"]
          query_string_cache_keys = forwarded_values.value["query_string_cache_keys"]

          dynamic "cookies" {
            for_each = forwarded_values.value.cookies
            content {
              forward           = cookies.value["forward"]
              whitelisted_names = cookies.value["whitelisted_names"]
            }
          }

        }
      }

      dynamic "lambda_function_association" {
        for_each = ordered_cache_behavior.value.lambda_function_association
        content {
          event_type   = lambda_function_association.value["event_type"]
          include_body = lambda_function_association.value["include_body"]
          lambda_arn   = lambda_function_association.value["lambda_arn"]
        }
      }

    }
  }

  dynamic "origin" {
    for_each = var.origin
    content {
      domain_name = origin.value["domain_name"]
      origin_id   = origin.value["origin_id"]
      origin_path = origin.value["origin_path"]

      dynamic "custom_header" {
        for_each = origin.value.custom_header
        content {
          name  = custom_header.value["name"]
          value = custom_header.value["value"]
        }
      }

      dynamic "custom_origin_config" {
        for_each = origin.value.custom_origin_config
        content {
          http_port                = custom_origin_config.value["http_port"]
          https_port               = custom_origin_config.value["https_port"]
          origin_keepalive_timeout = custom_origin_config.value["origin_keepalive_timeout"]
          origin_protocol_policy   = custom_origin_config.value["origin_protocol_policy"]
          origin_read_timeout      = custom_origin_config.value["origin_read_timeout"]
          origin_ssl_protocols     = custom_origin_config.value["origin_ssl_protocols"]
        }
      }

      dynamic "s3_origin_config" {
        for_each = origin.value.s3_origin_config
        content {
          origin_access_identity = s3_origin_config.value["origin_access_identity"]
        }
      }

    }
  }

  dynamic "origin_group" {
    for_each = var.origin_group
    content {
      origin_id = origin_group.value["origin_id"]

      dynamic "failover_criteria" {
        for_each = origin_group.value.failover_criteria
        content {
          status_codes = failover_criteria.value["status_codes"]
        }
      }

      dynamic "member" {
        for_each = origin_group.value.member
        content {
          origin_id = member.value["origin_id"]
        }
      }

    }
  }

  dynamic "restrictions" {
    for_each = var.restrictions
    content {

      dynamic "geo_restriction" {
        for_each = restrictions.value.geo_restriction
        content {
          locations        = geo_restriction.value["locations"]
          restriction_type = geo_restriction.value["restriction_type"]
        }
      }

    }
  }

  dynamic "viewer_certificate" {
    for_each = var.viewer_certificate
    content {
      acm_certificate_arn            = viewer_certificate.value["acm_certificate_arn"]
      cloudfront_default_certificate = viewer_certificate.value["cloudfront_default_certificate"]
      iam_certificate_id             = viewer_certificate.value["iam_certificate_id"]
      minimum_protocol_version       = viewer_certificate.value["minimum_protocol_version"]
      ssl_support_method             = viewer_certificate.value["ssl_support_method"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.arn
}

output "caller_reference" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.caller_reference
}

output "domain_name" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.domain_name
}

output "etag" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.etag
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.id
}

output "in_progress_validation_batches" {
  description = "returns a number"
  value       = aws_cloudfront_distribution.this.in_progress_validation_batches
}

output "last_modified_time" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.last_modified_time
}

output "status" {
  description = "returns a string"
  value       = aws_cloudfront_distribution.this.status
}

output "trusted_signers" {
  description = "returns a list of object"
  value       = aws_cloudfront_distribution.this.trusted_signers
}

output "this" {
  value = aws_cloudfront_distribution.this
}
```

[top](#index)