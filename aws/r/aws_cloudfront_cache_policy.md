# aws_cloudfront_cache_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_cloudfront_cache_policy" {
  source = "./modules/aws/r/aws_cloudfront_cache_policy"

  # comment - (optional) is a type of string
  comment = null
  # default_ttl - (optional) is a type of number
  default_ttl = null
  # etag - (optional) is a type of string
  etag = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # min_ttl - (optional) is a type of number
  min_ttl = null
  # name - (required) is a type of string
  name = null

  parameters_in_cache_key_and_forwarded_to_origin = [{
    cookies_config = [{
      cookie_behavior = null
      cookies = [{
        items = []
      }]
    }]
    enable_accept_encoding_brotli = null
    enable_accept_encoding_gzip   = null
    headers_config = [{
      header_behavior = null
      headers = [{
        items = []
      }]
    }]
    query_strings_config = [{
      query_string_behavior = null
      query_strings = [{
        items = []
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "etag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters_in_cache_key_and_forwarded_to_origin" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookies_config = list(object(
        {
          cookie_behavior = string
          cookies = list(object(
            {
              items = set(string)
            }
          ))
        }
      ))
      enable_accept_encoding_brotli = bool
      enable_accept_encoding_gzip   = bool
      headers_config = list(object(
        {
          header_behavior = string
          headers = list(object(
            {
              items = set(string)
            }
          ))
        }
      ))
      query_strings_config = list(object(
        {
          query_string_behavior = string
          query_strings = list(object(
            {
              items = set(string)
            }
          ))
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
resource "aws_cloudfront_cache_policy" "this" {
  comment     = var.comment
  default_ttl = var.default_ttl
  etag        = var.etag
  max_ttl     = var.max_ttl
  min_ttl     = var.min_ttl
  name        = var.name

  dynamic "parameters_in_cache_key_and_forwarded_to_origin" {
    for_each = var.parameters_in_cache_key_and_forwarded_to_origin
    content {
      enable_accept_encoding_brotli = parameters_in_cache_key_and_forwarded_to_origin.value["enable_accept_encoding_brotli"]
      enable_accept_encoding_gzip   = parameters_in_cache_key_and_forwarded_to_origin.value["enable_accept_encoding_gzip"]

      dynamic "cookies_config" {
        for_each = parameters_in_cache_key_and_forwarded_to_origin.value.cookies_config
        content {
          cookie_behavior = cookies_config.value["cookie_behavior"]

          dynamic "cookies" {
            for_each = cookies_config.value.cookies
            content {
              items = cookies.value["items"]
            }
          }

        }
      }

      dynamic "headers_config" {
        for_each = parameters_in_cache_key_and_forwarded_to_origin.value.headers_config
        content {
          header_behavior = headers_config.value["header_behavior"]

          dynamic "headers" {
            for_each = headers_config.value.headers
            content {
              items = headers.value["items"]
            }
          }

        }
      }

      dynamic "query_strings_config" {
        for_each = parameters_in_cache_key_and_forwarded_to_origin.value.query_strings_config
        content {
          query_string_behavior = query_strings_config.value["query_string_behavior"]

          dynamic "query_strings" {
            for_each = query_strings_config.value.query_strings
            content {
              items = query_strings.value["items"]
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
output "etag" {
  description = "returns a string"
  value       = aws_cloudfront_cache_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = aws_cloudfront_cache_policy.this.id
}

output "this" {
  value = aws_cloudfront_cache_policy.this
}
```

[top](#index)