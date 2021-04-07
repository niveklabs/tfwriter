# aws_cognito_user_pool_client

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
module "aws_cognito_user_pool_client" {
  source = "./modules/aws/r/aws_cognito_user_pool_client"

  # access_token_validity - (optional) is a type of number
  access_token_validity = null
  # allowed_oauth_flows - (optional) is a type of set of string
  allowed_oauth_flows = []
  # allowed_oauth_flows_user_pool_client - (optional) is a type of bool
  allowed_oauth_flows_user_pool_client = null
  # allowed_oauth_scopes - (optional) is a type of set of string
  allowed_oauth_scopes = []
  # callback_urls - (optional) is a type of set of string
  callback_urls = []
  # default_redirect_uri - (optional) is a type of string
  default_redirect_uri = null
  # explicit_auth_flows - (optional) is a type of set of string
  explicit_auth_flows = []
  # generate_secret - (optional) is a type of bool
  generate_secret = null
  # id_token_validity - (optional) is a type of number
  id_token_validity = null
  # logout_urls - (optional) is a type of set of string
  logout_urls = []
  # name - (required) is a type of string
  name = null
  # prevent_user_existence_errors - (optional) is a type of string
  prevent_user_existence_errors = null
  # read_attributes - (optional) is a type of set of string
  read_attributes = []
  # refresh_token_validity - (optional) is a type of number
  refresh_token_validity = null
  # supported_identity_providers - (optional) is a type of set of string
  supported_identity_providers = []
  # user_pool_id - (required) is a type of string
  user_pool_id = null
  # write_attributes - (optional) is a type of set of string
  write_attributes = []

  analytics_configuration = [{
    application_arn  = null
    application_id   = null
    external_id      = null
    role_arn         = null
    user_data_shared = null
  }]

  token_validity_units = [{
    access_token  = null
    id_token      = null
    refresh_token = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_token_validity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "allowed_oauth_flows" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "allowed_oauth_flows_user_pool_client" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allowed_oauth_scopes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "callback_urls" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "default_redirect_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "explicit_auth_flows" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "generate_secret" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "id_token_validity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "logout_urls" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "prevent_user_existence_errors" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "read_attributes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "refresh_token_validity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "supported_identity_providers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "user_pool_id" {
  description = "(required)"
  type        = string
}

variable "write_attributes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "analytics_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      application_arn  = string
      application_id   = string
      external_id      = string
      role_arn         = string
      user_data_shared = bool
    }
  ))
  default = []
}

variable "token_validity_units" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access_token  = string
      id_token      = string
      refresh_token = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cognito_user_pool_client" "this" {
  # access_token_validity - (optional) is a type of number
  access_token_validity = var.access_token_validity
  # allowed_oauth_flows - (optional) is a type of set of string
  allowed_oauth_flows = var.allowed_oauth_flows
  # allowed_oauth_flows_user_pool_client - (optional) is a type of bool
  allowed_oauth_flows_user_pool_client = var.allowed_oauth_flows_user_pool_client
  # allowed_oauth_scopes - (optional) is a type of set of string
  allowed_oauth_scopes = var.allowed_oauth_scopes
  # callback_urls - (optional) is a type of set of string
  callback_urls = var.callback_urls
  # default_redirect_uri - (optional) is a type of string
  default_redirect_uri = var.default_redirect_uri
  # explicit_auth_flows - (optional) is a type of set of string
  explicit_auth_flows = var.explicit_auth_flows
  # generate_secret - (optional) is a type of bool
  generate_secret = var.generate_secret
  # id_token_validity - (optional) is a type of number
  id_token_validity = var.id_token_validity
  # logout_urls - (optional) is a type of set of string
  logout_urls = var.logout_urls
  # name - (required) is a type of string
  name = var.name
  # prevent_user_existence_errors - (optional) is a type of string
  prevent_user_existence_errors = var.prevent_user_existence_errors
  # read_attributes - (optional) is a type of set of string
  read_attributes = var.read_attributes
  # refresh_token_validity - (optional) is a type of number
  refresh_token_validity = var.refresh_token_validity
  # supported_identity_providers - (optional) is a type of set of string
  supported_identity_providers = var.supported_identity_providers
  # user_pool_id - (required) is a type of string
  user_pool_id = var.user_pool_id
  # write_attributes - (optional) is a type of set of string
  write_attributes = var.write_attributes

  dynamic "analytics_configuration" {
    for_each = var.analytics_configuration
    content {
      # application_arn - (optional) is a type of string
      application_arn = analytics_configuration.value["application_arn"]
      # application_id - (optional) is a type of string
      application_id = analytics_configuration.value["application_id"]
      # external_id - (optional) is a type of string
      external_id = analytics_configuration.value["external_id"]
      # role_arn - (optional) is a type of string
      role_arn = analytics_configuration.value["role_arn"]
      # user_data_shared - (optional) is a type of bool
      user_data_shared = analytics_configuration.value["user_data_shared"]
    }
  }

  dynamic "token_validity_units" {
    for_each = var.token_validity_units
    content {
      # access_token - (optional) is a type of string
      access_token = token_validity_units.value["access_token"]
      # id_token - (optional) is a type of string
      id_token = token_validity_units.value["id_token"]
      # refresh_token - (optional) is a type of string
      refresh_token = token_validity_units.value["refresh_token"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "client_secret" {
  description = "returns a string"
  value       = aws_cognito_user_pool_client.this.client_secret
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = aws_cognito_user_pool_client.this.id
}

output "prevent_user_existence_errors" {
  description = "returns a string"
  value       = aws_cognito_user_pool_client.this.prevent_user_existence_errors
}

output "this" {
  value = aws_cognito_user_pool_client.this
}
```

[top](#index)