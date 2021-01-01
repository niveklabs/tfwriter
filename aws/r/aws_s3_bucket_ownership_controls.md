# aws_s3_bucket_ownership_controls

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
module "aws_s3_bucket_ownership_controls" {
  source = "./modules/aws/r/aws_s3_bucket_ownership_controls"

  # bucket - (required) is a type of string
  bucket = null

  rule = [{
    object_ownership = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "rule" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      object_ownership = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_s3_bucket_ownership_controls" "this" {
  bucket = var.bucket

  dynamic "rule" {
    for_each = var.rule
    content {
      object_ownership = rule.value["object_ownership"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_ownership_controls.this.id
}

output "this" {
  value = aws_s3_bucket_ownership_controls.this
}
```

[top](#index)