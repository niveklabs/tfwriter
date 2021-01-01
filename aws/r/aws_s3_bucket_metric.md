# aws_s3_bucket_metric
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
```hcl
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
```hcl
resource "aws_s3_bucket_metric" "this" {
  bucket = var.bucket
  name   = var.name

  dynamic "filter" {
    for_each = var.filter
    content {
      prefix = filter.value["prefix"]
      tags   = filter.value["tags"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_s3_bucket_metric.this.id
}

output "this" {
  value = aws_s3_bucket_metric.this
}
```
[top](#index)
