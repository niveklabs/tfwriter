# aws_cloudfront_cache_policy

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
module "aws_cloudfront_cache_policy" {
  source = "./modules/aws/d/aws_cloudfront_cache_policy"

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
data "aws_cloudfront_cache_policy" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "comment" {
  description = "returns a string"
  value       = data.aws_cloudfront_cache_policy.this.comment
}

output "default_ttl" {
  description = "returns a number"
  value       = data.aws_cloudfront_cache_policy.this.default_ttl
}

output "etag" {
  description = "returns a string"
  value       = data.aws_cloudfront_cache_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = data.aws_cloudfront_cache_policy.this.id
}

output "max_ttl" {
  description = "returns a number"
  value       = data.aws_cloudfront_cache_policy.this.max_ttl
}

output "min_ttl" {
  description = "returns a number"
  value       = data.aws_cloudfront_cache_policy.this.min_ttl
}

output "parameters_in_cache_key_and_forwarded_to_origin" {
  description = "returns a list of object"
  value       = data.aws_cloudfront_cache_policy.this.parameters_in_cache_key_and_forwarded_to_origin
}

output "this" {
  value = aws_cloudfront_cache_policy.this
}
```

[top](#index)