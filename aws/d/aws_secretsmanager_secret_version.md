# aws_secretsmanager_secret_version

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_secretsmanager_secret_version" {
  source = "./modules/aws/d/aws_secretsmanager_secret_version"

  # secret_id - (required) is a type of string
  secret_id = null
  # version_id - (optional) is a type of string
  version_id = null
  # version_stage - (optional) is a type of string
  version_stage = null
}
```

[top](#index)

### Variables

```terraform
variable "secret_id" {
  description = "(required)"
  type        = string
}

variable "version_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_stage" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_secretsmanager_secret_version" "this" {
  secret_id     = var.secret_id
  version_id    = var.version_id
  version_stage = var.version_stage
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_version.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_version.this.id
}

output "secret_binary" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_version.this.secret_binary
  sensitive   = true
}

output "secret_string" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_version.this.secret_string
  sensitive   = true
}

output "version_id" {
  description = "returns a string"
  value       = data.aws_secretsmanager_secret_version.this.version_id
}

output "version_stages" {
  description = "returns a set of string"
  value       = data.aws_secretsmanager_secret_version.this.version_stages
}

output "this" {
  value = aws_secretsmanager_secret_version.this
}
```

[top](#index)