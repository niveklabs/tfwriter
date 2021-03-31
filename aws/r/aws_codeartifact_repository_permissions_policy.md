# aws_codeartifact_repository_permissions_policy

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
module "aws_codeartifact_repository_permissions_policy" {
  source = "./modules/aws/r/aws_codeartifact_repository_permissions_policy"

  # domain - (required) is a type of string
  domain = null
  # domain_owner - (optional) is a type of string
  domain_owner = null
  # policy_document - (required) is a type of string
  policy_document = null
  # policy_revision - (optional) is a type of string
  policy_revision = null
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

variable "policy_document" {
  description = "(required)"
  type        = string
}

variable "policy_revision" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_codeartifact_repository_permissions_policy" "this" {
  domain          = var.domain
  domain_owner    = var.domain_owner
  policy_document = var.policy_document
  policy_revision = var.policy_revision
  repository      = var.repository
}
```

[top](#index)

### Outputs

```terraform
output "domain_owner" {
  description = "returns a string"
  value       = aws_codeartifact_repository_permissions_policy.this.domain_owner
}

output "id" {
  description = "returns a string"
  value       = aws_codeartifact_repository_permissions_policy.this.id
}

output "policy_revision" {
  description = "returns a string"
  value       = aws_codeartifact_repository_permissions_policy.this.policy_revision
}

output "resource_arn" {
  description = "returns a string"
  value       = aws_codeartifact_repository_permissions_policy.this.resource_arn
}

output "this" {
  value = aws_codeartifact_repository_permissions_policy.this
}
```

[top](#index)