# akamai_iam_user

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_iam_user" {
  source = "./modules/akamai/r/akamai_iam_user"

  # address - (optional) is a type of string
  address = null
  # auth_grants_json - (required) is a type of string
  auth_grants_json = null
  # city - (optional) is a type of string
  city = null
  # contact_type - (optional) is a type of string
  contact_type = null
  # country - (required) is a type of string
  country = null
  # email - (required) is a type of string
  email = null
  # enable_tfa - (required) is a type of bool
  enable_tfa = null
  # first_name - (required) is a type of string
  first_name = null
  # job_title - (optional) is a type of string
  job_title = null
  # last_name - (required) is a type of string
  last_name = null
  # mobile_phone - (optional) is a type of string
  mobile_phone = null
  # phone - (required) is a type of string
  phone = null
  # preferred_language - (optional) is a type of string
  preferred_language = null
  # secondary_email - (optional) is a type of string
  secondary_email = null
  # session_timeout - (optional) is a type of number
  session_timeout = null
  # state - (optional) is a type of string
  state = null
  # time_zone - (optional) is a type of string
  time_zone = null
  # zip_code - (optional) is a type of string
  zip_code = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(optional) - The user's street address"
  type        = string
  default     = null
}

variable "auth_grants_json" {
  description = "(required) - A user's per-group role assignments, in JSON form"
  type        = string
}

variable "city" {
  description = "(optional) - The user's city"
  type        = string
  default     = null
}

variable "contact_type" {
  description = "(optional) - To help characterize the user, the value can be any that are available from the view-contact-types operation"
  type        = string
  default     = null
}

variable "country" {
  description = "(required) - As part of the user's location, the value can be any that are available from the view-supported-countries operation"
  type        = string
}

variable "email" {
  description = "(required) - The user's email address"
  type        = string
}

variable "enable_tfa" {
  description = "(required) - Indicates whether two-factor authentication is allowed"
  type        = bool
}

variable "first_name" {
  description = "(required) - The user's first name"
  type        = string
}

variable "job_title" {
  description = "(optional) - The user's position at your company"
  type        = string
  default     = null
}

variable "last_name" {
  description = "(required) - The user's surname"
  type        = string
}

variable "mobile_phone" {
  description = "(optional) - The user's mobile phone number"
  type        = string
  default     = null
}

variable "phone" {
  description = "(required) - The user's main phone number"
  type        = string
}

variable "preferred_language" {
  description = "(optional) - The value can be any that are available from the view-languages operation"
  type        = string
  default     = null
}

variable "secondary_email" {
  description = "(optional) - The user's secondary email address"
  type        = string
  default     = null
}

variable "session_timeout" {
  description = "(optional) - The number of seconds it takes for the user's Control Center session to time out if there hasn't been any activity"
  type        = number
  default     = null
}

variable "state" {
  description = "(optional) - The user's state"
  type        = string
  default     = null
}

variable "time_zone" {
  description = "(optional) - The user's time zone. The value can be any that are available from the view-time-zones operation"
  type        = string
  default     = null
}

variable "zip_code" {
  description = "(optional) - The user's five-digit ZIP code"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "akamai_iam_user" "this" {
  # address - (optional) is a type of string
  address = var.address
  # auth_grants_json - (required) is a type of string
  auth_grants_json = var.auth_grants_json
  # city - (optional) is a type of string
  city = var.city
  # contact_type - (optional) is a type of string
  contact_type = var.contact_type
  # country - (required) is a type of string
  country = var.country
  # email - (required) is a type of string
  email = var.email
  # enable_tfa - (required) is a type of bool
  enable_tfa = var.enable_tfa
  # first_name - (required) is a type of string
  first_name = var.first_name
  # job_title - (optional) is a type of string
  job_title = var.job_title
  # last_name - (required) is a type of string
  last_name = var.last_name
  # mobile_phone - (optional) is a type of string
  mobile_phone = var.mobile_phone
  # phone - (required) is a type of string
  phone = var.phone
  # preferred_language - (optional) is a type of string
  preferred_language = var.preferred_language
  # secondary_email - (optional) is a type of string
  secondary_email = var.secondary_email
  # session_timeout - (optional) is a type of number
  session_timeout = var.session_timeout
  # state - (optional) is a type of string
  state = var.state
  # time_zone - (optional) is a type of string
  time_zone = var.time_zone
  # zip_code - (optional) is a type of string
  zip_code = var.zip_code
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = akamai_iam_user.this.address
}

output "contact_type" {
  description = "returns a string"
  value       = akamai_iam_user.this.contact_type
}

output "email_update_pending" {
  description = "returns a bool"
  value       = akamai_iam_user.this.email_update_pending
}

output "id" {
  description = "returns a string"
  value       = akamai_iam_user.this.id
}

output "is_locked" {
  description = "returns a bool"
  value       = akamai_iam_user.this.is_locked
}

output "last_login" {
  description = "returns a string"
  value       = akamai_iam_user.this.last_login
}

output "password_expired_after" {
  description = "returns a string"
  value       = akamai_iam_user.this.password_expired_after
}

output "preferred_language" {
  description = "returns a string"
  value       = akamai_iam_user.this.preferred_language
}

output "session_timeout" {
  description = "returns a number"
  value       = akamai_iam_user.this.session_timeout
}

output "tfa_configured" {
  description = "returns a bool"
  value       = akamai_iam_user.this.tfa_configured
}

output "time_zone" {
  description = "returns a string"
  value       = akamai_iam_user.this.time_zone
}

output "user_name" {
  description = "returns a string"
  value       = akamai_iam_user.this.user_name
}

output "this" {
  value = akamai_iam_user.this
}
```

[top](#index)