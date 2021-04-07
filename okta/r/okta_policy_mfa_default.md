# okta_policy_mfa_default

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
module "okta_policy_mfa_default" {
  source = "./modules/okta/r/okta_policy_mfa_default"

  # duo - (optional) is a type of map of string
  duo = {}
  # fido_u2f - (optional) is a type of map of string
  fido_u2f = {}
  # fido_webauthn - (optional) is a type of map of string
  fido_webauthn = {}
  # google_otp - (optional) is a type of map of string
  google_otp = {}
  # hotp - (optional) is a type of map of string
  hotp = {}
  # okta_call - (optional) is a type of map of string
  okta_call = {}
  # okta_email - (optional) is a type of map of string
  okta_email = {}
  # okta_otp - (optional) is a type of map of string
  okta_otp = {}
  # okta_password - (optional) is a type of map of string
  okta_password = {}
  # okta_push - (optional) is a type of map of string
  okta_push = {}
  # okta_question - (optional) is a type of map of string
  okta_question = {}
  # okta_sms - (optional) is a type of map of string
  okta_sms = {}
  # rsa_token - (optional) is a type of map of string
  rsa_token = {}
  # symantec_vip - (optional) is a type of map of string
  symantec_vip = {}
  # yubikey_token - (optional) is a type of map of string
  yubikey_token = {}
}
```

[top](#index)

### Variables

```terraform
variable "duo" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "fido_u2f" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "fido_webauthn" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "google_otp" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hotp" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_call" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_email" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_otp" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_password" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_push" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_question" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "okta_sms" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "rsa_token" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "symantec_vip" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "yubikey_token" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_policy_mfa_default" "this" {
  # duo - (optional) is a type of map of string
  duo = var.duo
  # fido_u2f - (optional) is a type of map of string
  fido_u2f = var.fido_u2f
  # fido_webauthn - (optional) is a type of map of string
  fido_webauthn = var.fido_webauthn
  # google_otp - (optional) is a type of map of string
  google_otp = var.google_otp
  # hotp - (optional) is a type of map of string
  hotp = var.hotp
  # okta_call - (optional) is a type of map of string
  okta_call = var.okta_call
  # okta_email - (optional) is a type of map of string
  okta_email = var.okta_email
  # okta_otp - (optional) is a type of map of string
  okta_otp = var.okta_otp
  # okta_password - (optional) is a type of map of string
  okta_password = var.okta_password
  # okta_push - (optional) is a type of map of string
  okta_push = var.okta_push
  # okta_question - (optional) is a type of map of string
  okta_question = var.okta_question
  # okta_sms - (optional) is a type of map of string
  okta_sms = var.okta_sms
  # rsa_token - (optional) is a type of map of string
  rsa_token = var.rsa_token
  # symantec_vip - (optional) is a type of map of string
  symantec_vip = var.symantec_vip
  # yubikey_token - (optional) is a type of map of string
  yubikey_token = var.yubikey_token
}
```

[top](#index)

### Outputs

```terraform
output "default_included_group_id" {
  description = "returns a string"
  value       = okta_policy_mfa_default.this.default_included_group_id
}

output "description" {
  description = "returns a string"
  value       = okta_policy_mfa_default.this.description
}

output "id" {
  description = "returns a string"
  value       = okta_policy_mfa_default.this.id
}

output "name" {
  description = "returns a string"
  value       = okta_policy_mfa_default.this.name
}

output "priority" {
  description = "returns a number"
  value       = okta_policy_mfa_default.this.priority
}

output "status" {
  description = "returns a string"
  value       = okta_policy_mfa_default.this.status
}

output "this" {
  value = okta_policy_mfa_default.this
}
```

[top](#index)