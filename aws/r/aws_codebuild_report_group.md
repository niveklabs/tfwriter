# aws_codebuild_report_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_codebuild_report_group" {
  source = "./modules/aws/r/aws_codebuild_report_group"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null

  export_config = [{
    s3_destination = [{
      bucket              = null
      encryption_disabled = null
      encryption_key      = null
      packaging           = null
      path                = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "export_config" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      s3_destination = list(object(
        {
          bucket              = string
          encryption_disabled = bool
          encryption_key      = string
          packaging           = string
          path                = string
        }
      ))
      type = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_codebuild_report_group" "this" {
  name = var.name
  tags = var.tags
  type = var.type

  dynamic "export_config" {
    for_each = var.export_config
    content {
      type = export_config.value["type"]

      dynamic "s3_destination" {
        for_each = export_config.value.s3_destination
        content {
          bucket              = s3_destination.value["bucket"]
          encryption_disabled = s3_destination.value["encryption_disabled"]
          encryption_key      = s3_destination.value["encryption_key"]
          packaging           = s3_destination.value["packaging"]
          path                = s3_destination.value["path"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_codebuild_report_group.this.arn
}

output "created" {
  description = "returns a string"
  value       = aws_codebuild_report_group.this.created
}

output "id" {
  description = "returns a string"
  value       = aws_codebuild_report_group.this.id
}

output "this" {
  value = aws_codebuild_report_group.this
}
```

[top](#index)