# aws_s3_bucket_policy

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3_bucket_policy" {
  source = "./modules/aws/r/aws_s3_bucket_policy"

  # bucket - (required) is a type of string
  bucket = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_policy" "this" {
  bucket = var.bucket
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_policy.this.id
}

output "this" {
  value = aws_s3_bucket_policy.this
}
```

[top](#index)