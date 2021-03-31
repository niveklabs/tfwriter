# aws_ses_identity_policy

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ses_identity_policy" {
  source = "./modules/aws/r/aws_ses_identity_policy"

  # identity - (required) is a type of string
  identity = null
  # name - (required) is a type of string
  name = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "identity" {
  description = "(required)"
  type        = string
}

variable "name" {
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
resource "aws_ses_identity_policy" "this" {
  identity = var.identity
  name     = var.name
  policy   = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ses_identity_policy.this.id
}

output "this" {
  value = aws_ses_identity_policy.this
}
```

[top](#index)