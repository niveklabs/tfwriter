# aws_cognito_user_pool_domain

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_cognito_user_pool_domain" {
  source = "./modules/aws/r/aws_cognito_user_pool_domain"

  # certificate_arn - (optional) is a type of string
  certificate_arn = null
  # domain - (required) is a type of string
  domain = null
  # user_pool_id - (required) is a type of string
  user_pool_id = null
}
```

[top](#index)

### Variables

```hcl
variable "certificate_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "user_pool_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_cognito_user_pool_domain" "this" {
  certificate_arn = var.certificate_arn
  domain          = var.domain
  user_pool_id    = var.user_pool_id
}
```

[top](#index)

### Outputs

```hcl
output "aws_account_id" {
  description = "returns a string"
  value       = aws_cognito_user_pool_domain.this.aws_account_id
}

output "cloudfront_distribution_arn" {
  description = "returns a string"
  value       = aws_cognito_user_pool_domain.this.cloudfront_distribution_arn
}

output "id" {
  description = "returns a string"
  value       = aws_cognito_user_pool_domain.this.id
}

output "s3_bucket" {
  description = "returns a string"
  value       = aws_cognito_user_pool_domain.this.s3_bucket
}

output "version" {
  description = "returns a string"
  value       = aws_cognito_user_pool_domain.this.version
}

output "this" {
  value = aws_cognito_user_pool_domain.this
}
```

[top](#index)