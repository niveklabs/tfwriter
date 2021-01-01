# aws_cognito_resource_server

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
module "aws_cognito_resource_server" {
  source = "./modules/aws/r/aws_cognito_resource_server"

  # identifier - (required) is a type of string
  identifier = null
  # name - (required) is a type of string
  name = null
  # user_pool_id - (required) is a type of string
  user_pool_id = null

  scope = [{
    scope_description = null
    scope_name        = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "identifier" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "user_pool_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "nested mode: NestingSet, min items: 0, max items: 100"
  type = set(object(
    {
      scope_description = string
      scope_name        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_cognito_resource_server" "this" {
  identifier   = var.identifier
  name         = var.name
  user_pool_id = var.user_pool_id

  dynamic "scope" {
    for_each = var.scope
    content {
      scope_description = scope.value["scope_description"]
      scope_name        = scope.value["scope_name"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_cognito_resource_server.this.id
}

output "scope_identifiers" {
  description = "returns a list of string"
  value       = aws_cognito_resource_server.this.scope_identifiers
}

output "this" {
  value = aws_cognito_resource_server.this
}
```

[top](#index)