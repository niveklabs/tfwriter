# okta_password_policy

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
module "okta_password_policy" {
  source = "./modules/okta/r/okta_password_policy"

  # auth_provider - (optional) is a type of string
  auth_provider = null
  # call_recovery - (optional) is a type of string
  call_recovery = null
  # description - (optional) is a type of string
  description = null
  # email_recovery - (optional) is a type of string
  email_recovery = null
  # groups_included - (optional) is a type of set of string
  groups_included = []
  # name - (required) is a type of string
  name = null
  # password_auto_unlock_minutes - (optional) is a type of number
  password_auto_unlock_minutes = null
  # password_dictionary_lookup - (optional) is a type of bool
  password_dictionary_lookup = null
  # password_exclude_first_name - (optional) is a type of bool
  password_exclude_first_name = null
  # password_exclude_last_name - (optional) is a type of bool
  password_exclude_last_name = null
  # password_exclude_username - (optional) is a type of bool
  password_exclude_username = null
  # password_expire_warn_days - (optional) is a type of number
  password_expire_warn_days = null
  # password_history_count - (optional) is a type of number
  password_history_count = null
  # password_lockout_notification_channels - (optional) is a type of set of string
  password_lockout_notification_channels = []
  # password_max_age_days - (optional) is a type of number
  password_max_age_days = null
  # password_max_lockout_attempts - (optional) is a type of number
  password_max_lockout_attempts = null
  # password_min_age_minutes - (optional) is a type of number
  password_min_age_minutes = null
  # password_min_length - (optional) is a type of number
  password_min_length = null
  # password_min_lowercase - (optional) is a type of number
  password_min_lowercase = null
  # password_min_number - (optional) is a type of number
  password_min_number = null
  # password_min_symbol - (optional) is a type of number
  password_min_symbol = null
  # password_min_uppercase - (optional) is a type of number
  password_min_uppercase = null
  # password_show_lockout_failures - (optional) is a type of bool
  password_show_lockout_failures = null
  # priority - (optional) is a type of number
  priority = null
  # question_min_length - (optional) is a type of number
  question_min_length = null
  # question_recovery - (optional) is a type of string
  question_recovery = null
  # recovery_email_token - (optional) is a type of number
  recovery_email_token = null
  # skip_unlock - (optional) is a type of bool
  skip_unlock = null
  # sms_recovery - (optional) is a type of string
  sms_recovery = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_provider" {
  description = "(optional) - Authentication Provider: OKTA or ACTIVE_DIRECTORY."
  type        = string
  default     = null
}

variable "call_recovery" {
  description = "(optional) - Enable or disable voice call recovery: ACTIVE or INACTIVE."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Policy Description"
  type        = string
  default     = null
}

variable "email_recovery" {
  description = "(optional) - Enable or disable email password recovery: ACTIVE or INACTIVE."
  type        = string
  default     = null
}

variable "groups_included" {
  description = "(optional) - List of Group IDs to Include"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Policy Name"
  type        = string
}

variable "password_auto_unlock_minutes" {
  description = "(optional) - Number of minutes before a locked account is unlocked: 0 = no limit."
  type        = number
  default     = null
}

variable "password_dictionary_lookup" {
  description = "(optional) - Check Passwords Against Common Password Dictionary."
  type        = bool
  default     = null
}

variable "password_exclude_first_name" {
  description = "(optional) - User firstName attribute must be excluded from the password"
  type        = bool
  default     = null
}

variable "password_exclude_last_name" {
  description = "(optional) - User lastName attribute must be excluded from the password"
  type        = bool
  default     = null
}

variable "password_exclude_username" {
  description = "(optional) - If the user name must be excluded from the password."
  type        = bool
  default     = null
}

variable "password_expire_warn_days" {
  description = "(optional) - Length in days a user will be warned before password expiry: 0 = no warning."
  type        = number
  default     = null
}

variable "password_history_count" {
  description = "(optional) - Number of distinct passwords that must be created before they can be reused: 0 = none."
  type        = number
  default     = null
}

variable "password_lockout_notification_channels" {
  description = "(optional) - Notification channels to use to notify a user when their account has been locked."
  type        = set(string)
  default     = null
}

variable "password_max_age_days" {
  description = "(optional) - Length in days a password is valid before expiry: 0 = no limit."
  type        = number
  default     = null
}

variable "password_max_lockout_attempts" {
  description = "(optional) - Number of unsuccessful login attempts allowed before lockout: 0 = no limit."
  type        = number
  default     = null
}

variable "password_min_age_minutes" {
  description = "(optional) - Minimum time interval in minutes between password changes: 0 = no limit."
  type        = number
  default     = null
}

variable "password_min_length" {
  description = "(optional) - Minimum password length."
  type        = number
  default     = null
}

variable "password_min_lowercase" {
  description = "(optional) - If a password must contain at least one lower case letter: 0 = no, 1 = yes. Default = 1"
  type        = number
  default     = null
}

variable "password_min_number" {
  description = "(optional) - If a password must contain at least one number: 0 = no, 1 = yes. Default = 1"
  type        = number
  default     = null
}

variable "password_min_symbol" {
  description = "(optional) - If a password must contain at least one symbol (!@#$%^&*): 0 = no, 1 = yes. Default = 1"
  type        = number
  default     = null
}

variable "password_min_uppercase" {
  description = "(optional) - If a password must contain at least one upper case letter: 0 = no, 1 = yes. Default = 1"
  type        = number
  default     = null
}

variable "password_show_lockout_failures" {
  description = "(optional) - If a user should be informed when their account is locked."
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional) - Policy Priority, this attribute can be set to a valid priority. To avoid endless diff situation we error if an invalid priority is provided. API defaults it to the last (lowest) if not there."
  type        = number
  default     = null
}

variable "question_min_length" {
  description = "(optional) - Min length of the password recovery question answer."
  type        = number
  default     = null
}

variable "question_recovery" {
  description = "(optional) - Enable or disable security question password recovery: ACTIVE or INACTIVE."
  type        = string
  default     = null
}

variable "recovery_email_token" {
  description = "(optional) - Lifetime in minutes of the recovery email token."
  type        = number
  default     = null
}

variable "skip_unlock" {
  description = "(optional) - When an Active Directory user is locked out of Okta, the Okta unlock operation should also attempt to unlock the user's Windows account."
  type        = bool
  default     = null
}

variable "sms_recovery" {
  description = "(optional) - Enable or disable SMS password recovery: ACTIVE or INACTIVE."
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - Policy Status: ACTIVE or INACTIVE."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_password_policy" "this" {
  auth_provider                          = var.auth_provider
  call_recovery                          = var.call_recovery
  description                            = var.description
  email_recovery                         = var.email_recovery
  groups_included                        = var.groups_included
  name                                   = var.name
  password_auto_unlock_minutes           = var.password_auto_unlock_minutes
  password_dictionary_lookup             = var.password_dictionary_lookup
  password_exclude_first_name            = var.password_exclude_first_name
  password_exclude_last_name             = var.password_exclude_last_name
  password_exclude_username              = var.password_exclude_username
  password_expire_warn_days              = var.password_expire_warn_days
  password_history_count                 = var.password_history_count
  password_lockout_notification_channels = var.password_lockout_notification_channels
  password_max_age_days                  = var.password_max_age_days
  password_max_lockout_attempts          = var.password_max_lockout_attempts
  password_min_age_minutes               = var.password_min_age_minutes
  password_min_length                    = var.password_min_length
  password_min_lowercase                 = var.password_min_lowercase
  password_min_number                    = var.password_min_number
  password_min_symbol                    = var.password_min_symbol
  password_min_uppercase                 = var.password_min_uppercase
  password_show_lockout_failures         = var.password_show_lockout_failures
  priority                               = var.priority
  question_min_length                    = var.question_min_length
  question_recovery                      = var.question_recovery
  recovery_email_token                   = var.recovery_email_token
  skip_unlock                            = var.skip_unlock
  sms_recovery                           = var.sms_recovery
  status                                 = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_password_policy.this.id
}

output "this" {
  value = okta_password_policy.this
}
```

[top](#index)