# aws_cloudfront_origin_request_policy

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/aws/d/aws_cloudfront_origin_request_policy"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_cloudfront_origin_request_policy" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = data.aws_cloudfront_origin_request_policy.this.comment
}

output "cookies_config" {
  description = "returns a list of object"
  value       = data.aws_cloudfront_origin_request_policy.this.cookies_config
}

output "etag" {
  description = "returns a string"
  value       = data.aws_cloudfront_origin_request_policy.this.etag
}

output "headers_config" {
  description = "returns a list of object"
  value       = data.aws_cloudfront_origin_request_policy.this.headers_config
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudfront_origin_request_policy.this.id
}

output "query_strings_config" {
  description = "returns a list of object"
  value       = data.aws_cloudfront_origin_request_policy.this.query_strings_config
}

output "this" {
  value = aws_cloudfront_origin_request_policy.this
}
```

[top](#index)