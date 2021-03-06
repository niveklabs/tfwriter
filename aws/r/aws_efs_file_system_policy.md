# aws_efs_file_system_policy

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
module "aws_efs_file_system_policy" {
  source = "./modules/aws/r/aws_efs_file_system_policy"

  # file_system_id - (required) is a type of string
  file_system_id = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "file_system_id" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_efs_file_system_policy" "this" {
  # file_system_id - (required) is a type of string
  file_system_id = var.file_system_id
  # policy - (required) is a type of string
  policy = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_efs_file_system_policy.this.id
}

output "this" {
  value = aws_efs_file_system_policy.this
}
```

[top](#index)