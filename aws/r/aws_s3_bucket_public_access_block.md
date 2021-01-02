# aws_s3_bucket_public_access_block

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3_bucket_public_access_block" {
  source = "./modules/aws/r/aws_s3_bucket_public_access_block"

  # block_public_acls - (optional) is a type of bool
  block_public_acls = null
  # block_public_policy - (optional) is a type of bool
  block_public_policy = null
  # bucket - (required) is a type of string
  bucket = null
  # ignore_public_acls - (optional) is a type of bool
  ignore_public_acls = null
  # restrict_public_buckets - (optional) is a type of bool
  restrict_public_buckets = null
}
```

[top](#index)

### Variables

```terraform
variable "block_public_acls" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "block_public_policy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "bucket" {
  description = "(required)"
  type        = string
}

variable "ignore_public_acls" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "restrict_public_buckets" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_public_access_block" "this" {
  block_public_acls       = var.block_public_acls
  block_public_policy     = var.block_public_policy
  bucket                  = var.bucket
  ignore_public_acls      = var.ignore_public_acls
  restrict_public_buckets = var.restrict_public_buckets
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_public_access_block.this.id
}

output "this" {
  value = aws_s3_bucket_public_access_block.this
}
```

[top](#index)