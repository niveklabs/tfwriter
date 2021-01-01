# aws_ebs_snapshot_copy

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
module "aws_ebs_snapshot_copy" {
  source = "./modules/aws/r/aws_ebs_snapshot_copy"

  # description - (optional) is a type of string
  description = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # source_region - (required) is a type of string
  source_region = null
  # source_snapshot_id - (required) is a type of string
  source_snapshot_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_region" {
  description = "(required)"
  type        = string
}

variable "source_snapshot_id" {
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
resource "aws_ebs_snapshot_copy" "this" {
  description        = var.description
  encrypted          = var.encrypted
  kms_key_id         = var.kms_key_id
  source_region      = var.source_region
  source_snapshot_id = var.source_snapshot_id
  tags               = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ebs_snapshot_copy.this.arn
}

output "data_encryption_key_id" {
  description = "returns a string"
  value       = aws_ebs_snapshot_copy.this.data_encryption_key_id
}

output "id" {
  description = "returns a string"
  value       = aws_ebs_snapshot_copy.this.id
}

output "owner_alias" {
  description = "returns a string"
  value       = aws_ebs_snapshot_copy.this.owner_alias
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ebs_snapshot_copy.this.owner_id
}

output "volume_id" {
  description = "returns a string"
  value       = aws_ebs_snapshot_copy.this.volume_id
}

output "volume_size" {
  description = "returns a number"
  value       = aws_ebs_snapshot_copy.this.volume_size
}

output "this" {
  value = aws_ebs_snapshot_copy.this
}
```

[top](#index)