# vault_okta_auth_backend

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_okta_auth_backend" {
  source = "./modules/vault/r/vault_okta_auth_backend"

  # base_url - (optional) is a type of string
  base_url = null
  # bypass_okta_mfa - (optional) is a type of bool
  bypass_okta_mfa = null
  # description - (optional) is a type of string
  description = null
  # group - (optional) is a type of set of object
  group = [{
    group_name = null
    policies   = []
  }]
  # max_ttl - (optional) is a type of string
  max_ttl = null
  # organization - (required) is a type of string
  organization = null
  # path - (optional) is a type of string
  path = null
  # token - (optional) is a type of string
  token = null
  # ttl - (optional) is a type of string
  ttl = null
  # user - (optional) is a type of set of object
  user = [{
    groups   = []
    policies = []
    username = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "base_url" {
  description = "(optional) - The Okta url. Examples: oktapreview.com, okta.com (default)"
  type        = string
  default     = null
}

variable "bypass_okta_mfa" {
  description = "(optional) - When true, requests by Okta for a MFA check will be bypassed. This also disallows certain status checks on the account, such as whether the password is expired."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The description of the auth backend"
  type        = string
  default     = null
}

variable "group" {
  description = "(optional)"
  type = set(object(
    {
      group_name = string
      policies   = set(string)
    }
  ))
  default = null
}

variable "max_ttl" {
  description = "(optional) - Maximum duration after which authentication will be expired"
  type        = string
  default     = null
}

variable "organization" {
  description = "(required) - The Okta organization. This will be the first part of the url https://XXX.okta.com."
  type        = string
}

variable "path" {
  description = "(optional) - path to mount the backend"
  type        = string
  default     = null
}

variable "token" {
  description = "(optional) - The Okta API token. This is required to query Okta for user group membership. If this is not supplied only locally configured groups will be enabled."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - Duration after which authentication will be expired"
  type        = string
  default     = null
}

variable "user" {
  description = "(optional)"
  type = set(object(
    {
      groups   = set(string)
      policies = set(string)
      username = string
    }
  ))
  default = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_okta_auth_backend" "this" {
  # base_url - (optional) is a type of string
  base_url = var.base_url
  # bypass_okta_mfa - (optional) is a type of bool
  bypass_okta_mfa = var.bypass_okta_mfa
  # description - (optional) is a type of string
  description = var.description
  # group - (optional) is a type of set of object
  group = var.group
  # max_ttl - (optional) is a type of string
  max_ttl = var.max_ttl
  # organization - (required) is a type of string
  organization = var.organization
  # path - (optional) is a type of string
  path = var.path
  # token - (optional) is a type of string
  token = var.token
  # ttl - (optional) is a type of string
  ttl = var.ttl
  # user - (optional) is a type of set of object
  user = var.user
}
```

[top](#index)

### Outputs

```terraform
output "accessor" {
  description = "returns a string"
  value       = vault_okta_auth_backend.this.accessor
}

output "group" {
  description = "returns a set of object"
  value       = vault_okta_auth_backend.this.group
}

output "id" {
  description = "returns a string"
  value       = vault_okta_auth_backend.this.id
}

output "user" {
  description = "returns a set of object"
  value       = vault_okta_auth_backend.this.user
}

output "this" {
  value = vault_okta_auth_backend.this
}
```

[top](#index)