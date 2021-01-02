# aws_secretsmanager_secret_version

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_secretsmanager_secret_version" {
  source = "./modules/aws/r/aws_secretsmanager_secret_version"

  # secret_binary - (optional) is a type of string
  secret_binary = null
  # secret_id - (required) is a type of string
  secret_id = null
  # secret_string - (optional) is a type of string
  secret_string = null
  # version_stages - (optional) is a type of set of string
  version_stages = []
}
```

[top](#index)

### Variables

```terraform
variable "secret_binary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_id" {
  description = "(required)"
  type        = string
}

variable "secret_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_stages" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_secretsmanager_secret_version" "this" {
  secret_binary  = var.secret_binary
  secret_id      = var.secret_id
  secret_string  = var.secret_string
  version_stages = var.version_stages
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_secretsmanager_secret_version.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_secretsmanager_secret_version.this.id
}

output "version_id" {
  description = "returns a string"
  value       = aws_secretsmanager_secret_version.this.version_id
}

output "version_stages" {
  description = "returns a set of string"
  value       = aws_secretsmanager_secret_version.this.version_stages
}

output "this" {
  value = aws_secretsmanager_secret_version.this
}
```

[top](#index)