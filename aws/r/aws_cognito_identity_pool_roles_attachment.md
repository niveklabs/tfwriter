# aws_cognito_identity_pool_roles_attachment

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
module "aws_cognito_identity_pool_roles_attachment" {
  source = "./modules/aws/r/aws_cognito_identity_pool_roles_attachment"

  # identity_pool_id - (required) is a type of string
  identity_pool_id = null
  # roles - (required) is a type of map of string
  roles = {}

  role_mapping = [{
    ambiguous_role_resolution = null
    identity_provider         = null
    mapping_rule = [{
      claim      = null
      match_type = null
      role_arn   = null
      value      = null
    }]
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "identity_pool_id" {
  description = "(required)"
  type        = string
}

variable "roles" {
  description = "(required)"
  type        = map(string)
}

variable "role_mapping" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ambiguous_role_resolution = string
      identity_provider         = string
      mapping_rule = list(object(
        {
          claim      = string
          match_type = string
          role_arn   = string
          value      = string
        }
      ))
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cognito_identity_pool_roles_attachment" "this" {
  identity_pool_id = var.identity_pool_id
  roles            = var.roles

  dynamic "role_mapping" {
    for_each = var.role_mapping
    content {
      ambiguous_role_resolution = role_mapping.value["ambiguous_role_resolution"]
      identity_provider         = role_mapping.value["identity_provider"]
      type                      = role_mapping.value["type"]

      dynamic "mapping_rule" {
        for_each = role_mapping.value.mapping_rule
        content {
          claim      = mapping_rule.value["claim"]
          match_type = mapping_rule.value["match_type"]
          role_arn   = mapping_rule.value["role_arn"]
          value      = mapping_rule.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cognito_identity_pool_roles_attachment.this.id
}

output "this" {
  value = aws_cognito_identity_pool_roles_attachment.this
}
```

[top](#index)