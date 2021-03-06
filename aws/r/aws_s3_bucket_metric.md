# aws_s3_bucket_metric

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3_bucket_metric" {
  source = "./modules/aws/r/aws_s3_bucket_metric"

  # bucket - (required) is a type of string
  bucket = null
  # name - (required) is a type of string
  name = null

  filter = [{
    prefix = null
    tags   = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      prefix = string
      tags   = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket_metric" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # name - (required) is a type of string
  name = var.name

  dynamic "filter" {
    for_each = var.filter
    content {
      # prefix - (optional) is a type of string
      prefix = filter.value["prefix"]
      # tags - (optional) is a type of map of string
      tags = filter.value["tags"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_metric.this.id
}

output "this" {
  value = aws_s3_bucket_metric.this
}
```

[top](#index)