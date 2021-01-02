# aws_efs_access_point

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_efs_access_point" {
  source = "./modules/aws/d/aws_efs_access_point"

  # access_point_id - (required) is a type of string
  access_point_id = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "access_point_id" {
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

### Datasource

```terraform
data "aws_efs_access_point" "this" {
  access_point_id = var.access_point_id
  tags            = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_efs_access_point.this.arn
}

output "file_system_arn" {
  description = "returns a string"
  value       = data.aws_efs_access_point.this.file_system_arn
}

output "file_system_id" {
  description = "returns a string"
  value       = data.aws_efs_access_point.this.file_system_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_efs_access_point.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_efs_access_point.this.owner_id
}

output "posix_user" {
  description = "returns a list of object"
  value       = data.aws_efs_access_point.this.posix_user
}

output "root_directory" {
  description = "returns a list of object"
  value       = data.aws_efs_access_point.this.root_directory
}

output "this" {
  value = aws_efs_access_point.this
}
```

[top](#index)