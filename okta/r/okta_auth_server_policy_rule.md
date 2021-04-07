# okta_auth_server_policy_rule

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_auth_server_policy_rule" {
  source = "./modules/okta/r/okta_auth_server_policy_rule"

  # access_token_lifetime_minutes - (optional) is a type of number
  access_token_lifetime_minutes = null
  # auth_server_id - (required) is a type of string
  auth_server_id = null
  # grant_type_whitelist - (required) is a type of set of string
  grant_type_whitelist = []
  # group_blacklist - (optional) is a type of set of string
  group_blacklist = []
  # group_whitelist - (optional) is a type of set of string
  group_whitelist = []
  # inline_hook_id - (optional) is a type of string
  inline_hook_id = null
  # name - (required) is a type of string
  name = null
  # policy_id - (required) is a type of string
  policy_id = null
  # priority - (required) is a type of number
  priority = null
  # refresh_token_lifetime_minutes - (optional) is a type of number
  refresh_token_lifetime_minutes = null
  # refresh_token_window_minutes - (optional) is a type of number
  refresh_token_window_minutes = null
  # scope_whitelist - (optional) is a type of set of string
  scope_whitelist = []
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
  # user_blacklist - (optional) is a type of set of string
  user_blacklist = []
  # user_whitelist - (optional) is a type of set of string
  user_whitelist = []
}
```

[top](#index)

### Variables

```terraform
variable "access_token_lifetime_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_server_id" {
  description = "(required) - Auth server ID"
  type        = string
}

variable "grant_type_whitelist" {
  description = "(required) - Accepted grant type values: authorization_code, implicit, password, client_credentials"
  type        = set(string)
}

variable "group_blacklist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "group_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "inline_hook_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Auth server policy rule name"
  type        = string
}

variable "policy_id" {
  description = "(required) - Auth server policy ID"
  type        = string
}

variable "priority" {
  description = "(required) - Priority of the auth server policy rule"
  type        = number
}

variable "refresh_token_lifetime_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "refresh_token_window_minutes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "scope_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Auth server policy rule type, unlikely this will be anything other then the default"
  type        = string
  default     = null
}

variable "user_blacklist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "user_whitelist" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_auth_server_policy_rule" "this" {
  # access_token_lifetime_minutes - (optional) is a type of number
  access_token_lifetime_minutes = var.access_token_lifetime_minutes
  # auth_server_id - (required) is a type of string
  auth_server_id = var.auth_server_id
  # grant_type_whitelist - (required) is a type of set of string
  grant_type_whitelist = var.grant_type_whitelist
  # group_blacklist - (optional) is a type of set of string
  group_blacklist = var.group_blacklist
  # group_whitelist - (optional) is a type of set of string
  group_whitelist = var.group_whitelist
  # inline_hook_id - (optional) is a type of string
  inline_hook_id = var.inline_hook_id
  # name - (required) is a type of string
  name = var.name
  # policy_id - (required) is a type of string
  policy_id = var.policy_id
  # priority - (required) is a type of number
  priority = var.priority
  # refresh_token_lifetime_minutes - (optional) is a type of number
  refresh_token_lifetime_minutes = var.refresh_token_lifetime_minutes
  # refresh_token_window_minutes - (optional) is a type of number
  refresh_token_window_minutes = var.refresh_token_window_minutes
  # scope_whitelist - (optional) is a type of set of string
  scope_whitelist = var.scope_whitelist
  # status - (optional) is a type of string
  status = var.status
  # type - (optional) is a type of string
  type = var.type
  # user_blacklist - (optional) is a type of set of string
  user_blacklist = var.user_blacklist
  # user_whitelist - (optional) is a type of set of string
  user_whitelist = var.user_whitelist
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_auth_server_policy_rule.this.id
}

output "this" {
  value = okta_auth_server_policy_rule.this
}
```

[top](#index)