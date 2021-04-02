# aws_efs_access_points

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_efs_access_points" {
  source = "./modules/aws/d/aws_efs_access_points"

  # file_system_id - (required) is a type of string
  file_system_id = null
}
```

[top](#index)

### Variables

```terraform
variable "file_system_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_efs_access_points" "this" {
  file_system_id = var.file_system_id
}
```

[top](#index)

### Outputs

```terraform
output "arns" {
  description = "returns a set of string"
  value       = data.aws_efs_access_points.this.arns
}

output "id" {
  description = "returns a string"
  value       = data.aws_efs_access_points.this.id
}

output "ids" {
  description = "returns a set of string"
  value       = data.aws_efs_access_points.this.ids
}

output "this" {
  value = aws_efs_access_points.this
}
```

[top](#index)