# okta_idp

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
module "okta_idp" {
  source = "./modules/okta/r/okta_idp"

  # account_link_action - (optional) is a type of string
  account_link_action = null
  # account_link_group_include - (optional) is a type of set of string
  account_link_group_include = []
  # acs_binding - (required) is a type of string
  acs_binding = null
  # acs_type - (optional) is a type of string
  acs_type = null
  # authorization_binding - (required) is a type of string
  authorization_binding = null
  # authorization_url - (required) is a type of string
  authorization_url = null
  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
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
  # issuer_url - (required) is a type of string
  issuer_url = null
  # jwks_binding - (required) is a type of string
  jwks_binding = null
  # jwks_url - (required) is a type of string
  jwks_url = null
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
  # token_binding - (required) is a type of string
  token_binding = null
  # token_url - (required) is a type of string
  token_url = null
  # user_info_binding - (optional) is a type of string
  user_info_binding = null
  # user_info_url - (optional) is a type of string
  user_info_url = null
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

variable "acs_binding" {
  description = "(required)"
  type        = string
}

variable "acs_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authorization_binding" {
  description = "(required)"
  type        = string
}

variable "authorization_url" {
  description = "(required)"
  type        = string
}

variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(required)"
  type        = string
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

variable "issuer_url" {
  description = "(required)"
  type        = string
}

variable "jwks_binding" {
  description = "(required)"
  type        = string
}

variable "jwks_url" {
  description = "(required)"
  type        = string
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

variable "token_binding" {
  description = "(required)"
  type        = string
}

variable "token_url" {
  description = "(required)"
  type        = string
}

variable "user_info_binding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_info_url" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "okta_idp" "this" {
  account_link_action          = var.account_link_action
  account_link_group_include   = var.account_link_group_include
  acs_binding                  = var.acs_binding
  acs_type                     = var.acs_type
  authorization_binding        = var.authorization_binding
  authorization_url            = var.authorization_url
  client_id                    = var.client_id
  client_secret                = var.client_secret
  deprovisioned_action         = var.deprovisioned_action
  groups_action                = var.groups_action
  groups_assignment            = var.groups_assignment
  groups_attribute             = var.groups_attribute
  groups_filter                = var.groups_filter
  issuer_mode                  = var.issuer_mode
  issuer_url                   = var.issuer_url
  jwks_binding                 = var.jwks_binding
  jwks_url                     = var.jwks_url
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
  token_binding                = var.token_binding
  token_url                    = var.token_url
  user_info_binding            = var.user_info_binding
  user_info_url                = var.user_info_url
  username_template            = var.username_template
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_idp.this.id
}

output "type" {
  description = "returns a string"
  value       = okta_idp.this.type
}

output "this" {
  value = okta_idp.this
}
```

[top](#index)