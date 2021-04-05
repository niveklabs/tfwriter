# okta_app_oauth

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "okta_app_oauth" {
  source = "./modules/okta/d/okta_app_oauth"

  # active_only - (optional) is a type of bool
  active_only = null
  # groups - (optional) is a type of set of string
  groups = []
  # label - (optional) is a type of string
  label = null
  # label_prefix - (optional) is a type of string
  label_prefix = null
  # users - (optional) is a type of set of string
  users = []
}
```

[top](#index)

### Variables

```terraform
variable "active_only" {
  description = "(optional) - Search only ACTIVE applications."
  type        = bool
  default     = null
}

variable "groups" {
  description = "(optional) - Groups associated with the application"
  type        = set(string)
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "users" {
  description = "(optional) - Users associated with the application"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_app_oauth" "this" {
  active_only  = var.active_only
  groups       = var.groups
  label        = var.label
  label_prefix = var.label_prefix
  users        = var.users
}
```

[top](#index)

### Outputs

```terraform
output "auto_submit_toolbar" {
  description = "returns a bool"
  value       = data.okta_app_oauth.this.auto_submit_toolbar
}

output "client_id" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.client_id
}

output "client_uri" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.client_uri
}

output "grant_types" {
  description = "returns a set of string"
  value       = data.okta_app_oauth.this.grant_types
}

output "hide_ios" {
  description = "returns a bool"
  value       = data.okta_app_oauth.this.hide_ios
}

output "hide_web" {
  description = "returns a bool"
  value       = data.okta_app_oauth.this.hide_web
}

output "id" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.id
}

output "links" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.links
}

output "login_mode" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.login_mode
}

output "login_scopes" {
  description = "returns a set of string"
  value       = data.okta_app_oauth.this.login_scopes
}

output "login_uri" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.login_uri
}

output "logo_uri" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.logo_uri
}

output "name" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.name
}

output "policy_uri" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.policy_uri
}

output "post_logout_redirect_uris" {
  description = "returns a set of string"
  value       = data.okta_app_oauth.this.post_logout_redirect_uris
}

output "redirect_uris" {
  description = "returns a set of string"
  value       = data.okta_app_oauth.this.redirect_uris
}

output "response_types" {
  description = "returns a set of string"
  value       = data.okta_app_oauth.this.response_types
}

output "status" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.status
}

output "type" {
  description = "returns a string"
  value       = data.okta_app_oauth.this.type
}

output "this" {
  value = okta_app_oauth.this
}
```

[top](#index)