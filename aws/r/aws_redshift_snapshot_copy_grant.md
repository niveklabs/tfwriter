# aws_redshift_snapshot_copy_grant

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
module "aws_redshift_snapshot_copy_grant" {
  source = "./modules/aws/r/aws_redshift_snapshot_copy_grant"

  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # snapshot_copy_grant_name - (required) is a type of string
  snapshot_copy_grant_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_copy_grant_name" {
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

```terraform
resource "aws_redshift_snapshot_copy_grant" "this" {
  kms_key_id               = var.kms_key_id
  snapshot_copy_grant_name = var.snapshot_copy_grant_name
  tags                     = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_redshift_snapshot_copy_grant.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_redshift_snapshot_copy_grant.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = aws_redshift_snapshot_copy_grant.this.kms_key_id
}

output "this" {
  value = aws_redshift_snapshot_copy_grant.this
}
```

[top](#index)