# aws_codecommit_repository

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
module "aws_codecommit_repository" {
  source = "./modules/aws/d/aws_codecommit_repository"

  # repository_name - (required) is a type of string
  repository_name = null
}
```

[top](#index)

### Variables

```terraform
variable "repository_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_codecommit_repository" "this" {
  # repository_name - (required) is a type of string
  repository_name = var.repository_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_codecommit_repository.this.arn
}

output "clone_url_http" {
  description = "returns a string"
  value       = data.aws_codecommit_repository.this.clone_url_http
}

output "clone_url_ssh" {
  description = "returns a string"
  value       = data.aws_codecommit_repository.this.clone_url_ssh
}

output "id" {
  description = "returns a string"
  value       = data.aws_codecommit_repository.this.id
}

output "repository_id" {
  description = "returns a string"
  value       = data.aws_codecommit_repository.this.repository_id
}

output "this" {
  value = aws_codecommit_repository.this
}
```

[top](#index)