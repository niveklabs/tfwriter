# okta_mfa_policy

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
module "okta_mfa_policy" {
  source = "./modules/okta/r/okta_mfa_policy"

  # description - (optional) is a type of string
  description = null
  # duo - (optional) is a type of map of string
  duo = {}
  # fido_u2f - (optional) is a type of map of string
  fido_u2f = {}
  # fido_webauthn - (optional) is a type of map of string
  fido_webauthn = {}
  # google_otp - (optional) is a type of map of string
  google_otp = {}
  # groups_included - (optional) is a type of set of string
  groups_included = []
  # hotp - (optional) is a type of map of string
  hotp = {}
  # name - (required) is a type of string
  name = null
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
  # priority - (optional) is a type of number
  priority = null
  # rsa_token - (optional) is a type of map of string
  rsa_token = {}
  # status - (optional) is a type of string
  status = null
  # symantec_vip - (optional) is a type of map of string
  symantec_vip = {}
  # yubikey_token - (optional) is a type of map of string
  yubikey_token = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Policy Description"
  type        = string
  default     = null
}

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

variable "groups_included" {
  description = "(optional) - List of Group IDs to Include"
  type        = set(string)
  default     = null
}

variable "hotp" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Policy Name"
  type        = string
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

variable "priority" {
  description = "(optional) - Policy Priority, this attribute can be set to a valid priority. To avoid endless diff situation we error if an invalid priority is provided. API defaults it to the last (lowest) if not there."
  type        = number
  default     = null
}

variable "rsa_token" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "status" {
  description = "(optional) - Policy Status: ACTIVE or INACTIVE."
  type        = string
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
resource "okta_mfa_policy" "this" {
  description     = var.description
  duo             = var.duo
  fido_u2f        = var.fido_u2f
  fido_webauthn   = var.fido_webauthn
  google_otp      = var.google_otp
  groups_included = var.groups_included
  hotp            = var.hotp
  name            = var.name
  okta_call       = var.okta_call
  okta_email      = var.okta_email
  okta_otp        = var.okta_otp
  okta_password   = var.okta_password
  okta_push       = var.okta_push
  okta_question   = var.okta_question
  okta_sms        = var.okta_sms
  priority        = var.priority
  rsa_token       = var.rsa_token
  status          = var.status
  symantec_vip    = var.symantec_vip
  yubikey_token   = var.yubikey_token
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_mfa_policy.this.id
}

output "this" {
  value = okta_mfa_policy.this
}
```

[top](#index)