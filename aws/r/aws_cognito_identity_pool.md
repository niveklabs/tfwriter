# aws_cognito_identity_pool

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
module "aws_cognito_identity_pool" {
  source = "./modules/aws/r/aws_cognito_identity_pool"

  # allow_unauthenticated_identities - (optional) is a type of bool
  allow_unauthenticated_identities = null
  # developer_provider_name - (optional) is a type of string
  developer_provider_name = null
  # identity_pool_name - (required) is a type of string
  identity_pool_name = null
  # openid_connect_provider_arns - (optional) is a type of set of string
  openid_connect_provider_arns = []
  # saml_provider_arns - (optional) is a type of list of string
  saml_provider_arns = []
  # supported_login_providers - (optional) is a type of map of string
  supported_login_providers = {}
  # tags - (optional) is a type of map of string
  tags = {}

  cognito_identity_providers = [{
    client_id               = null
    provider_name           = null
    server_side_token_check = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_unauthenticated_identities" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "developer_provider_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_pool_name" {
  description = "(required)"
  type        = string
}

variable "openid_connect_provider_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "saml_provider_arns" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "supported_login_providers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cognito_identity_providers" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      client_id               = string
      provider_name           = string
      server_side_token_check = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cognito_identity_pool" "this" {
  allow_unauthenticated_identities = var.allow_unauthenticated_identities
  developer_provider_name          = var.developer_provider_name
  identity_pool_name               = var.identity_pool_name
  openid_connect_provider_arns     = var.openid_connect_provider_arns
  saml_provider_arns               = var.saml_provider_arns
  supported_login_providers        = var.supported_login_providers
  tags                             = var.tags

  dynamic "cognito_identity_providers" {
    for_each = var.cognito_identity_providers
    content {
      client_id               = cognito_identity_providers.value["client_id"]
      provider_name           = cognito_identity_providers.value["provider_name"]
      server_side_token_check = cognito_identity_providers.value["server_side_token_check"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cognito_identity_pool.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_cognito_identity_pool.this.id
}

output "this" {
  value = aws_cognito_identity_pool.this
}
```

[top](#index)