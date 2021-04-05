# okta_idp_saml

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
module "okta_idp_saml" {
  source = "./modules/okta/r/okta_idp_saml"

  # account_link_action - (optional) is a type of string
  account_link_action = null
  # account_link_group_include - (optional) is a type of set of string
  account_link_group_include = []
  # acs_binding - (optional) is a type of string
  acs_binding = null
  # acs_type - (optional) is a type of string
  acs_type = null
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
  # issuer - (required) is a type of string
  issuer = null
  # issuer_mode - (optional) is a type of string
  issuer_mode = null
  # kid - (required) is a type of string
  kid = null
  # max_clock_skew - (optional) is a type of number
  max_clock_skew = null
  # name - (required) is a type of string
  name = null
  # name_format - (optional) is a type of string
  name_format = null
  # profile_master - (optional) is a type of bool
  profile_master = null
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
  # sso_binding - (optional) is a type of string
  sso_binding = null
  # sso_destination - (optional) is a type of string
  sso_destination = null
  # sso_url - (required) is a type of string
  sso_url = null
  # status - (optional) is a type of string
  status = null
  # subject_filter - (optional) is a type of string
  subject_filter = null
  # subject_format - (optional) is a type of set of string
  subject_format = []
  # subject_match_attribute - (optional) is a type of string
  subject_match_attribute = null
  # subject_match_type - (optional) is a type of string
  subject_match_type = null
  # suspended_action - (optional) is a type of string
  suspended_action = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "acs_type" {
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

variable "issuer" {
  description = "(required)"
  type        = string
}

variable "issuer_mode" {
  description = "(optional) - Indicates whether Okta uses the original Okta org domain URL, or a custom domain URL"
  type        = string
  default     = null
}

variable "kid" {
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

variable "name_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_master" {
  description = "(optional)"
  type        = bool
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

variable "sso_binding" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sso_url" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subject_format" {
  description = "(optional)"
  type        = set(string)
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

variable "username_template" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_idp_saml" "this" {
  account_link_action          = var.account_link_action
  account_link_group_include   = var.account_link_group_include
  acs_binding                  = var.acs_binding
  acs_type                     = var.acs_type
  deprovisioned_action         = var.deprovisioned_action
  groups_action                = var.groups_action
  groups_assignment            = var.groups_assignment
  groups_attribute             = var.groups_attribute
  groups_filter                = var.groups_filter
  issuer                       = var.issuer
  issuer_mode                  = var.issuer_mode
  kid                          = var.kid
  max_clock_skew               = var.max_clock_skew
  name                         = var.name
  name_format                  = var.name_format
  profile_master               = var.profile_master
  provisioning_action          = var.provisioning_action
  request_signature_algorithm  = var.request_signature_algorithm
  request_signature_scope      = var.request_signature_scope
  response_signature_algorithm = var.response_signature_algorithm
  response_signature_scope     = var.response_signature_scope
  sso_binding                  = var.sso_binding
  sso_destination              = var.sso_destination
  sso_url                      = var.sso_url
  status                       = var.status
  subject_filter               = var.subject_filter
  subject_format               = var.subject_format
  subject_match_attribute      = var.subject_match_attribute
  subject_match_type           = var.subject_match_type
  suspended_action             = var.suspended_action
  username_template            = var.username_template
}
```

[top](#index)

### Outputs

```terraform
output "audience" {
  description = "returns a string"
  value       = okta_idp_saml.this.audience
}

output "id" {
  description = "returns a string"
  value       = okta_idp_saml.this.id
}

output "type" {
  description = "returns a string"
  value       = okta_idp_saml.this.type
}

output "this" {
  value = okta_idp_saml.this
}
```

[top](#index)