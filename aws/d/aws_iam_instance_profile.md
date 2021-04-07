# aws_iam_instance_profile

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
module "aws_iam_instance_profile" {
  source = "./modules/aws/d/aws_iam_instance_profile"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_iam_instance_profile" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.arn
}

output "create_date" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.create_date
}

output "id" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.id
}

output "path" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.path
}

output "role_arn" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.role_arn
}

output "role_id" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.role_id
}

output "role_name" {
  description = "returns a string"
  value       = data.aws_iam_instance_profile.this.role_name
}

output "this" {
  value = aws_iam_instance_profile.this
}
```

[top](#index)