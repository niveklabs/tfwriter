# aws_cloudfront_origin_request_policy

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
module "aws_cloudfront_origin_request_policy" {
  source = "./modules/aws/r/aws_cloudfront_origin_request_policy"

  # comment - (optional) is a type of string
  comment = null
  # etag - (optional) is a type of string
  etag = null
  # name - (required) is a type of string
  name = null

  cookies_config = [{
    cookie_behavior = null
    cookies = [{
      items = []
    }]
  }]

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

variable "etag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "cookies_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cookie_behavior = string
      cookies = list(object(
        {
          items = set(string)
        }
      ))
    }
  ))
}

variable "headers_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      header_behavior = string
      headers = list(object(
        {
          items = set(string)
        }
      ))
    }
  ))
}

variable "query_strings_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
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
```

[top](#index)

### Resource

```terraform
resource "aws_cloudfront_origin_request_policy" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # etag - (optional) is a type of string
  etag = var.etag
  # name - (required) is a type of string
  name = var.name

  dynamic "cookies_config" {
    for_each = var.cookies_config
    content {
      # cookie_behavior - (required) is a type of string
      cookie_behavior = cookies_config.value["cookie_behavior"]

      dynamic "cookies" {
        for_each = cookies_config.value.cookies
        content {
          # items - (optional) is a type of set of string
          items = cookies.value["items"]
        }
      }

    }
  }

  dynamic "headers_config" {
    for_each = var.headers_config
    content {
      # header_behavior - (optional) is a type of string
      header_behavior = headers_config.value["header_behavior"]

      dynamic "headers" {
        for_each = headers_config.value.headers
        content {
          # items - (optional) is a type of set of string
          items = headers.value["items"]
        }
      }

    }
  }

  dynamic "query_strings_config" {
    for_each = var.query_strings_config
    content {
      # query_string_behavior - (required) is a type of string
      query_string_behavior = query_strings_config.value["query_string_behavior"]

      dynamic "query_strings" {
        for_each = query_strings_config.value.query_strings
        content {
          # items - (optional) is a type of set of string
          items = query_strings.value["items"]
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
  value       = aws_cloudfront_origin_request_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = aws_cloudfront_origin_request_policy.this.id
}

output "this" {
  value = aws_cloudfront_origin_request_policy.this
}
```

[top](#index)