# aws_iam_instance_profile

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
module "aws_iam_instance_profile" {
  source = "./modules/aws/r/aws_iam_instance_profile"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # path - (optional) is a type of string
  path = null
  # role - (optional) is a type of string
  role = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_iam_instance_profile" "this" {
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # path - (optional) is a type of string
  path = var.path
  # role - (optional) is a type of string
  role = var.role
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.arn
}

output "create_date" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.create_date
}

output "id" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.name
}

output "unique_id" {
  description = "returns a string"
  value       = aws_iam_instance_profile.this.unique_id
}

output "this" {
  value = aws_iam_instance_profile.this
}
```

[top](#index)