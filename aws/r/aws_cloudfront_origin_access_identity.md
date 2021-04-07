# aws_cloudfront_origin_access_identity

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
module "aws_cloudfront_origin_access_identity" {
  source = "./modules/aws/r/aws_cloudfront_origin_access_identity"

  # comment - (optional) is a type of string
  comment = null
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
```

[top](#index)

### Resource

```terraform
resource "aws_cloudfront_origin_access_identity" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
}
```

[top](#index)

### Outputs

```terraform
output "caller_reference" {
  description = "returns a string"
  value       = aws_cloudfront_origin_access_identity.this.caller_reference
}

output "cloudfront_access_identity_path" {
  description = "returns a string"
  value       = aws_cloudfront_origin_access_identity.this.cloudfront_access_identity_path
}

output "etag" {
  description = "returns a string"
  value       = aws_cloudfront_origin_access_identity.this.etag
}

output "iam_arn" {
  description = "returns a string"
  value       = aws_cloudfront_origin_access_identity.this.iam_arn
}

output "id" {
  description = "returns a string"
  value       = aws_cloudfront_origin_access_identity.this.id
}

output "s3_canonical_user_id" {
  description = "returns a string"
  value       = aws_cloudfront_origin_access_identity.this.s3_canonical_user_id
}

output "this" {
  value = aws_cloudfront_origin_access_identity.this
}
```

[top](#index)