# aws_s3_bucket

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
module "aws_s3_bucket" {
  source = "./modules/aws/d/aws_s3_bucket"

  # bucket - (required) is a type of string
  bucket = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_s3_bucket" "this" {
  bucket = var.bucket
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.arn
}

output "bucket_domain_name" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.bucket_domain_name
}

output "bucket_regional_domain_name" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.bucket_regional_domain_name
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.id
}

output "region" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.region
}

output "website_domain" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.website_domain
}

output "website_endpoint" {
  description = "returns a string"
  value       = data.aws_s3_bucket.this.website_endpoint
}

output "this" {
  value = aws_s3_bucket.this
}
```

[top](#index)