# launchdarkly_access_token

[back](../launchdarkly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    launchdarkly = ">= 1.5.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "launchdarkly_access_token" {
  source = "./modules/launchdarkly/r/launchdarkly_access_token"

  # custom_roles - (optional) is a type of set of string
  custom_roles = []
  # default_api_version - (optional) is a type of number
  default_api_version = null
  # expire - (optional) is a type of number
  expire = null
  # name - (required) is a type of string
  name = null
  # role - (optional) is a type of string
  role = null
  # service_token - (optional) is a type of bool
  service_token = null

  policy_statements = [{
    actions       = []
    effect        = null
    not_actions   = []
    not_resources = []
    resources     = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_roles" {
  description = "(optional) - A set of custom role keys to use as access limits for the access token"
  type        = set(string)
  default     = null
}

variable "default_api_version" {
  description = "(optional) - The default API version for this token. Defaults to the latest API version."
  type        = number
  default     = null
}

variable "expire" {
  description = "(optional) - Replace the computed token secret with a new value. The expired secret will no longer be able to authorize usage of the LaunchDarkly API. Should be an expiration time for the current token secret, expressed as a Unix epoch time in milliseconds. Setting this to a negative value will expire the existing token immediately. To reset the token value again, change 'expire' to a new value. Setting this field at resource creation time WILL NOT set an expiration time for the token."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the access token"
  type        = string
}

variable "role" {
  description = "(optional) - The name of a built-in role for the token"
  type        = string
  default     = null
}

variable "service_token" {
  description = "(optional) - Whether the token will be a service token https://docs.launchdarkly.com/home/account-security/api-access-tokens#service-tokens"
  type        = bool
  default     = null
}

variable "policy_statements" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      actions       = list(string)
      effect        = string
      not_actions   = list(string)
      not_resources = list(string)
      resources     = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "launchdarkly_access_token" "this" {
  # custom_roles - (optional) is a type of set of string
  custom_roles = var.custom_roles
  # default_api_version - (optional) is a type of number
  default_api_version = var.default_api_version
  # expire - (optional) is a type of number
  expire = var.expire
  # name - (required) is a type of string
  name = var.name
  # role - (optional) is a type of string
  role = var.role
  # service_token - (optional) is a type of bool
  service_token = var.service_token

  dynamic "policy_statements" {
    for_each = var.policy_statements
    content {
      # actions - (optional) is a type of list of string
      actions = policy_statements.value["actions"]
      # effect - (required) is a type of string
      effect = policy_statements.value["effect"]
      # not_actions - (optional) is a type of list of string
      not_actions = policy_statements.value["not_actions"]
      # not_resources - (optional) is a type of list of string
      not_resources = policy_statements.value["not_resources"]
      # resources - (optional) is a type of list of string
      resources = policy_statements.value["resources"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_api_version" {
  description = "returns a number"
  value       = launchdarkly_access_token.this.default_api_version
}

output "id" {
  description = "returns a string"
  value       = launchdarkly_access_token.this.id
}

output "token" {
  description = "returns a string"
  value       = launchdarkly_access_token.this.token
  sensitive   = true
}

output "this" {
  value = launchdarkly_access_token.this
}
```

[top](#index)