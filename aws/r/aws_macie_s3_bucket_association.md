# aws_macie_s3_bucket_association

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
module "aws_macie_s3_bucket_association" {
  source = "./modules/aws/r/aws_macie_s3_bucket_association"

  # bucket_name - (required) is a type of string
  bucket_name = null
  # member_account_id - (optional) is a type of string
  member_account_id = null
  # prefix - (optional) is a type of string
  prefix = null

  classification_type = [{
    continuous = null
    one_time   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket_name" {
  description = "(required)"
  type        = string
}

variable "member_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "classification_type" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      continuous = string
      one_time   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_macie_s3_bucket_association" "this" {
  bucket_name       = var.bucket_name
  member_account_id = var.member_account_id
  prefix            = var.prefix

  dynamic "classification_type" {
    for_each = var.classification_type
    content {
      continuous = classification_type.value["continuous"]
      one_time   = classification_type.value["one_time"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_macie_s3_bucket_association.this.id
}

output "this" {
  value = aws_macie_s3_bucket_association.this
}
```

[top](#index)