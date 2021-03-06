# aws_codeartifact_repository

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
module "aws_codeartifact_repository" {
  source = "./modules/aws/r/aws_codeartifact_repository"

  # description - (optional) is a type of string
  description = null
  # domain - (required) is a type of string
  domain = null
  # domain_owner - (optional) is a type of string
  domain_owner = null
  # repository - (required) is a type of string
  repository = null
  # tags - (optional) is a type of map of string
  tags = {}

  external_connections = [{
    external_connection_name = null
    package_format           = null
    status                   = null
  }]

  upstream = [{
    repository_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "domain_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "external_connections" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      external_connection_name = string
      package_format           = string
      status                   = string
    }
  ))
  default = []
}

variable "upstream" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      repository_name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_codeartifact_repository" "this" {
  # description - (optional) is a type of string
  description = var.description
  # domain - (required) is a type of string
  domain = var.domain
  # domain_owner - (optional) is a type of string
  domain_owner = var.domain_owner
  # repository - (required) is a type of string
  repository = var.repository
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "external_connections" {
    for_each = var.external_connections
    content {
      # external_connection_name - (required) is a type of string
      external_connection_name = external_connections.value["external_connection_name"]
    }
  }

  dynamic "upstream" {
    for_each = var.upstream
    content {
      # repository_name - (required) is a type of string
      repository_name = upstream.value["repository_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "administrator_account" {
  description = "returns a string"
  value       = aws_codeartifact_repository.this.administrator_account
}

output "arn" {
  description = "returns a string"
  value       = aws_codeartifact_repository.this.arn
}

output "domain_owner" {
  description = "returns a string"
  value       = aws_codeartifact_repository.this.domain_owner
}

output "id" {
  description = "returns a string"
  value       = aws_codeartifact_repository.this.id
}

output "this" {
  value = aws_codeartifact_repository.this
}
```

[top](#index)