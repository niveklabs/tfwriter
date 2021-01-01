# aws_iam_group

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
module "aws_iam_group" {
  source = "./modules/aws/r/aws_iam_group"

  # name - (required) is a type of string
  name = null
  # path - (optional) is a type of string
  path = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_iam_group" "this" {
  name = var.name
  path = var.path
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_iam_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_iam_group.this.id
}

output "unique_id" {
  description = "returns a string"
  value       = aws_iam_group.this.unique_id
}

output "this" {
  value = aws_iam_group.this
}
```

[top](#index)