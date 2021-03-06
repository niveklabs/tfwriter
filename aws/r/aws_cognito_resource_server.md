# aws_cognito_resource_server

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

```terraform
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
  description = "nested block: NestingSet, min items: 0, max items: 100"
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

```terraform
resource "aws_cognito_resource_server" "this" {
  # identifier - (required) is a type of string
  identifier = var.identifier
  # name - (required) is a type of string
  name = var.name
  # user_pool_id - (required) is a type of string
  user_pool_id = var.user_pool_id

  dynamic "scope" {
    for_each = var.scope
    content {
      # scope_description - (required) is a type of string
      scope_description = scope.value["scope_description"]
      # scope_name - (required) is a type of string
      scope_name = scope.value["scope_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
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