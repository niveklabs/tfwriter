# aws_s3control_bucket

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
module "aws_s3control_bucket" {
  source = "./modules/aws/r/aws_s3control_bucket"

  # bucket - (required) is a type of string
  bucket = null
  # outpost_id - (required) is a type of string
  outpost_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "outpost_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_s3control_bucket" "this" {
  bucket     = var.bucket
  outpost_id = var.outpost_id
  tags       = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_s3control_bucket.this.arn
}

output "creation_date" {
  description = "returns a string"
  value       = aws_s3control_bucket.this.creation_date
}

output "id" {
  description = "returns a string"
  value       = aws_s3control_bucket.this.id
}

output "public_access_block_enabled" {
  description = "returns a bool"
  value       = aws_s3control_bucket.this.public_access_block_enabled
}

output "this" {
  value = aws_s3control_bucket.this
}
```

[top](#index)