# aws_codeartifact_repository_endpoint

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
module "aws_codeartifact_repository_endpoint" {
  source = "./modules/aws/d/aws_codeartifact_repository_endpoint"

  # domain - (required) is a type of string
  domain = null
  # domain_owner - (optional) is a type of string
  domain_owner = null
  # format - (required) is a type of string
  format = null
  # repository - (required) is a type of string
  repository = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "domain_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(required)"
  type        = string
}

variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_codeartifact_repository_endpoint" "this" {
  domain       = var.domain
  domain_owner = var.domain_owner
  format       = var.format
  repository   = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "domain_owner" {
  description = "returns a string"
  value       = data.aws_codeartifact_repository_endpoint.this.domain_owner
}

output "id" {
  description = "returns a string"
  value       = data.aws_codeartifact_repository_endpoint.this.id
}

output "repository_endpoint" {
  description = "returns a string"
  value       = data.aws_codeartifact_repository_endpoint.this.repository_endpoint
}

output "this" {
  value = aws_codeartifact_repository_endpoint.this
}
```

[top](#index)