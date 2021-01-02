# aws_s3_access_point

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
module "aws_s3_access_point" {
  source = "./modules/aws/r/aws_s3_access_point"

  # account_id - (optional) is a type of string
  account_id = null
  # bucket - (required) is a type of string
  bucket = null
  # name - (required) is a type of string
  name = null
  # policy - (optional) is a type of string
  policy = null

  public_access_block_configuration = [{
    block_public_acls       = null
    block_public_policy     = null
    ignore_public_acls      = null
    restrict_public_buckets = null
  }]

  vpc_configuration = [{
    vpc_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bucket" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_access_block_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      block_public_acls       = bool
      block_public_policy     = bool
      ignore_public_acls      = bool
      restrict_public_buckets = bool
    }
  ))
  default = []
}

variable "vpc_configuration" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      vpc_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_access_point" "this" {
  account_id = var.account_id
  bucket     = var.bucket
  name       = var.name
  policy     = var.policy

  dynamic "public_access_block_configuration" {
    for_each = var.public_access_block_configuration
    content {
      block_public_acls       = public_access_block_configuration.value["block_public_acls"]
      block_public_policy     = public_access_block_configuration.value["block_public_policy"]
      ignore_public_acls      = public_access_block_configuration.value["ignore_public_acls"]
      restrict_public_buckets = public_access_block_configuration.value["restrict_public_buckets"]
    }
  }

  dynamic "vpc_configuration" {
    for_each = var.vpc_configuration
    content {
      vpc_id = vpc_configuration.value["vpc_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = aws_s3_access_point.this.account_id
}

output "arn" {
  description = "returns a string"
  value       = aws_s3_access_point.this.arn
}

output "domain_name" {
  description = "returns a string"
  value       = aws_s3_access_point.this.domain_name
}

output "has_public_access_policy" {
  description = "returns a bool"
  value       = aws_s3_access_point.this.has_public_access_policy
}

output "id" {
  description = "returns a string"
  value       = aws_s3_access_point.this.id
}

output "network_origin" {
  description = "returns a string"
  value       = aws_s3_access_point.this.network_origin
}

output "this" {
  value = aws_s3_access_point.this
}
```

[top](#index)