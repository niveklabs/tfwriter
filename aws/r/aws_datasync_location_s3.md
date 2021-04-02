# aws_datasync_location_s3

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
module "aws_datasync_location_s3" {
  source = "./modules/aws/r/aws_datasync_location_s3"

  # s3_bucket_arn - (required) is a type of string
  s3_bucket_arn = null
  # subdirectory - (required) is a type of string
  subdirectory = null
  # tags - (optional) is a type of map of string
  tags = {}

  s3_config = [{
    bucket_access_role_arn = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "s3_bucket_arn" {
  description = "(required)"
  type        = string
}

variable "subdirectory" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "s3_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      bucket_access_role_arn = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_datasync_location_s3" "this" {
  s3_bucket_arn = var.s3_bucket_arn
  subdirectory  = var.subdirectory
  tags          = var.tags

  dynamic "s3_config" {
    for_each = var.s3_config
    content {
      bucket_access_role_arn = s3_config.value["bucket_access_role_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_datasync_location_s3.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_location_s3.this.id
}

output "uri" {
  description = "returns a string"
  value       = aws_datasync_location_s3.this.uri
}

output "this" {
  value = aws_datasync_location_s3.this
}
```

[top](#index)