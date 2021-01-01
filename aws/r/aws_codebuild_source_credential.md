# aws_codebuild_source_credential

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
module "aws_codebuild_source_credential" {
  source = "./modules/aws/r/aws_codebuild_source_credential"

  # auth_type - (required) is a type of string
  auth_type = null
  # server_type - (required) is a type of string
  server_type = null
  # token - (required) is a type of string
  token = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```hcl
variable "auth_type" {
  description = "(required)"
  type        = string
}

variable "server_type" {
  description = "(required)"
  type        = string
}

variable "token" {
  description = "(required)"
  type        = string
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_codebuild_source_credential" "this" {
  auth_type   = var.auth_type
  server_type = var.server_type
  token       = var.token
  user_name   = var.user_name
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_codebuild_source_credential.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_codebuild_source_credential.this.id
}

output "this" {
  value = aws_codebuild_source_credential.this
}
```

[top](#index)