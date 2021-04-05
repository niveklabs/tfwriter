# okta_idp_social

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
module "okta_idp_social" {
  source = "./modules/okta/d/okta_idp_social"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - name of the IdP"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_idp_social" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "account_link_action" {
  description = "returns a string"
  value       = data.okta_idp_social.this.account_link_action
}

output "account_link_group_include" {
  description = "returns a set of string"
  value       = data.okta_idp_social.this.account_link_group_include
}

output "authorization_binding" {
  description = "returns a string"
  value       = data.okta_idp_social.this.authorization_binding
}

output "authorization_url" {
  description = "returns a string"
  value       = data.okta_idp_social.this.authorization_url
}

output "client_id" {
  description = "returns a string"
  value       = data.okta_idp_social.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = data.okta_idp_social.this.client_secret
  sensitive   = true
}

output "deprovisioned_action" {
  description = "returns a string"
  value       = data.okta_idp_social.this.deprovisioned_action
}

output "groups_action" {
  description = "returns a string"
  value       = data.okta_idp_social.this.groups_action
}

output "groups_assignment" {
  description = "returns a set of string"
  value       = data.okta_idp_social.this.groups_assignment
}

output "groups_attribute" {
  description = "returns a string"
  value       = data.okta_idp_social.this.groups_attribute
}

output "groups_filter" {
  description = "returns a set of string"
  value       = data.okta_idp_social.this.groups_filter
}

output "id" {
  description = "returns a string"
  value       = data.okta_idp_social.this.id
}

output "issuer_mode" {
  description = "returns a string"
  value       = data.okta_idp_social.this.issuer_mode
}

output "max_clock_skew" {
  description = "returns a number"
  value       = data.okta_idp_social.this.max_clock_skew
}

output "profile_master" {
  description = "returns a bool"
  value       = data.okta_idp_social.this.profile_master
}

output "protocol_type" {
  description = "returns a string"
  value       = data.okta_idp_social.this.protocol_type
}

output "provisioning_action" {
  description = "returns a string"
  value       = data.okta_idp_social.this.provisioning_action
}

output "scopes" {
  description = "returns a set of string"
  value       = data.okta_idp_social.this.scopes
}

output "status" {
  description = "returns a string"
  value       = data.okta_idp_social.this.status
}

output "subject_match_attribute" {
  description = "returns a string"
  value       = data.okta_idp_social.this.subject_match_attribute
}

output "subject_match_type" {
  description = "returns a string"
  value       = data.okta_idp_social.this.subject_match_type
}

output "suspended_action" {
  description = "returns a string"
  value       = data.okta_idp_social.this.suspended_action
}

output "token_binding" {
  description = "returns a string"
  value       = data.okta_idp_social.this.token_binding
}

output "token_url" {
  description = "returns a string"
  value       = data.okta_idp_social.this.token_url
}

output "type" {
  description = "returns a string"
  value       = data.okta_idp_social.this.type
}

output "username_template" {
  description = "returns a string"
  value       = data.okta_idp_social.this.username_template
}

output "this" {
  value = okta_idp_social.this
}
```

[top](#index)