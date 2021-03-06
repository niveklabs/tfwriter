# aws_datasync_location_efs

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
module "aws_datasync_location_efs" {
  source = "./modules/aws/r/aws_datasync_location_efs"

  # efs_file_system_arn - (required) is a type of string
  efs_file_system_arn = null
  # subdirectory - (optional) is a type of string
  subdirectory = null
  # tags - (optional) is a type of map of string
  tags = {}

  ec2_config = [{
    security_group_arns = []
    subnet_arn          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "efs_file_system_arn" {
  description = "(required)"
  type        = string
}

variable "subdirectory" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ec2_config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      security_group_arns = set(string)
      subnet_arn          = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_datasync_location_efs" "this" {
  # efs_file_system_arn - (required) is a type of string
  efs_file_system_arn = var.efs_file_system_arn
  # subdirectory - (optional) is a type of string
  subdirectory = var.subdirectory
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "ec2_config" {
    for_each = var.ec2_config
    content {
      # security_group_arns - (required) is a type of set of string
      security_group_arns = ec2_config.value["security_group_arns"]
      # subnet_arn - (required) is a type of string
      subnet_arn = ec2_config.value["subnet_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_datasync_location_efs.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_location_efs.this.id
}

output "uri" {
  description = "returns a string"
  value       = aws_datasync_location_efs.this.uri
}

output "this" {
  value = aws_datasync_location_efs.this
}
```

[top](#index)