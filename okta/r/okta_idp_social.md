# okta_idp_social

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
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_idp_social" {
  source = "./modules/okta/r/okta_idp_social"

  # account_link_action - (optional) is a type of string
  account_link_action = null
  # account_link_group_include - (optional) is a type of set of string
  account_link_group_include = []
  # client_id - (optional) is a type of string
  client_id = null
  # client_secret - (optional) is a type of string
  client_secret = null
  # deprovisioned_action - (optional) is a type of string
  deprovisioned_action = null
  # groups_action - (optional) is a type of string
  groups_action = null
  # groups_assignment - (optional) is a type of set of string
  groups_assignment = []
  # groups_attribute - (optional) is a type of string
  groups_attribute = null
  # groups_filter - (optional) is a type of set of string
  groups_filter = []
  # issuer_mode - (optional) is a type of string
  issuer_mode = null
  # match_attribute - (optional) is a type of string
  match_attribute = null
  # match_type - (optional) is a type of string
  match_type = null
  # max_clock_skew - (optional) is a type of number
  max_clock_skew = null
  # name - (required) is a type of string
  name = null
  # profile_master - (optional) is a type of bool
  profile_master = null
  # protocol_type - (optional) is a type of string
  protocol_type = null
  # provisioning_action - (optional) is a type of string
  provisioning_action = null
  # request_signature_algorithm - (optional) is a type of string
  request_signature_algorithm = null
  # request_signature_scope - (optional) is a type of string
  request_signature_scope = null
  # response_signature_algorithm - (optional) is a type of string
  response_signature_algorithm = null
  # response_signature_scope - (optional) is a type of string
  response_signature_scope = null
  # scopes - (required) is a type of set of string
  scopes = []
  # status - (optional) is a type of string
  status = null
  # subject_match_attribute - (optional) is a type of string
  subject_match_attribute = null
  # subject_match_type - (optional) is a type of string
  subject_match_type = null
  # suspended_action - (optional) is a type of string
  suspended_action = null
  # type - (required) is a type of string
  type = null
  # username_template - (optional) is a type of string
  username_template = null
}
```

[top](#index)

### Variables

```terraform
variable "account_link_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_link_group_include" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "client_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deprovisioned_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups_assignment" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "groups_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups_filter" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "issuer_mode" {
  description = "(optional) - Indicates whether Okta uses the original Okta org domain URL, or a custom domain URL"
  type        = string
  default     = null
}

variable "match_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "match_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_clock_skew" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - name of idp"
  type        = string
}

variable "profile_master" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "protocol_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provisioning_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_signature_algorithm" {
  description = "(optional) - algorithm to use to sign requests"
  type        = string
  default     = null
}

variable "request_signature_scope" {
  description = "(optional) - algorithm to use to sign response"
  type        = string
  default     = null
}

variable "response_signature_algorithm" {
  description = "(optional) - algorithm to use to sign requests"
  type        = string
  default     = null
}

variable "response_signature_scope" {
  description = "(optional) - algorithm to use to sign response"
  type        = string
  default     = null
}

variable "scopes" {
  description = "(required)"
  type        = set(string)
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_match_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_match_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suspended_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "username_template" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_idp_social" "this" {
  account_link_action          = var.account_link_action
  account_link_group_include   = var.account_link_group_include
  client_id                    = var.client_id
  client_secret                = var.client_secret
  deprovisioned_action         = var.deprovisioned_action
  groups_action                = var.groups_action
  groups_assignment            = var.groups_assignment
  groups_attribute             = var.groups_attribute
  groups_filter                = var.groups_filter
  issuer_mode                  = var.issuer_mode
  match_attribute              = var.match_attribute
  match_type                   = var.match_type
  max_clock_skew               = var.max_clock_skew
  name                         = var.name
  profile_master               = var.profile_master
  protocol_type                = var.protocol_type
  provisioning_action          = var.provisioning_action
  request_signature_algorithm  = var.request_signature_algorithm
  request_signature_scope      = var.request_signature_scope
  response_signature_algorithm = var.response_signature_algorithm
  response_signature_scope     = var.response_signature_scope
  scopes                       = var.scopes
  status                       = var.status
  subject_match_attribute      = var.subject_match_attribute
  subject_match_type           = var.subject_match_type
  suspended_action             = var.suspended_action
  type                         = var.type
  username_template            = var.username_template
}
```

[top](#index)

### Outputs

```terraform
output "authorization_binding" {
  description = "returns a string"
  value       = okta_idp_social.this.authorization_binding
}

output "authorization_url" {
  description = "returns a string"
  value       = okta_idp_social.this.authorization_url
}

output "id" {
  description = "returns a string"
  value       = okta_idp_social.this.id
}

output "token_binding" {
  description = "returns a string"
  value       = okta_idp_social.this.token_binding
}

output "token_url" {
  description = "returns a string"
  value       = okta_idp_social.this.token_url
}

output "this" {
  value = okta_idp_social.this
}
```

[top](#index)