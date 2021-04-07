# okta_policy_rule_signon

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
module "okta_policy_rule_signon" {
  source = "./modules/okta/r/okta_policy_rule_signon"

  # access - (optional) is a type of string
  access = null
  # authtype - (optional) is a type of string
  authtype = null
  # mfa_lifetime - (optional) is a type of number
  mfa_lifetime = null
  # mfa_prompt - (optional) is a type of string
  mfa_prompt = null
  # mfa_remember_device - (optional) is a type of bool
  mfa_remember_device = null
  # mfa_required - (optional) is a type of bool
  mfa_required = null
  # name - (required) is a type of string
  name = null
  # network_connection - (optional) is a type of string
  network_connection = null
  # network_excludes - (optional) is a type of list of string
  network_excludes = []
  # network_includes - (optional) is a type of list of string
  network_includes = []
  # policyid - (required) is a type of string
  policyid = null
  # priority - (optional) is a type of number
  priority = null
  # session_idle - (optional) is a type of number
  session_idle = null
  # session_lifetime - (optional) is a type of number
  session_lifetime = null
  # session_persistent - (optional) is a type of bool
  session_persistent = null
  # status - (optional) is a type of string
  status = null
  # users_excluded - (optional) is a type of set of string
  users_excluded = []
}
```

[top](#index)

### Variables

```terraform
variable "access" {
  description = "(optional) - Allow or deny access based on the rule conditions: ALLOW or DENY."
  type        = string
  default     = null
}

variable "authtype" {
  description = "(optional) - Authentication entrypoint: ANY or RADIUS."
  type        = string
  default     = null
}

variable "mfa_lifetime" {
  description = "(optional) - Elapsed time before the next MFA challenge"
  type        = number
  default     = null
}

variable "mfa_prompt" {
  description = "(optional) - Prompt for MFA based on the device used, a factor session lifetime, or every sign-on attempt: DEVICE, SESSION or ALWAYS"
  type        = string
  default     = null
}

variable "mfa_remember_device" {
  description = "(optional) - Remember MFA device."
  type        = bool
  default     = null
}

variable "mfa_required" {
  description = "(optional) - Require MFA."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Policy Rule Name"
  type        = string
}

variable "network_connection" {
  description = "(optional) - Network selection mode: ANYWHERE, ZONE, ON_NETWORK, or OFF_NETWORK."
  type        = string
  default     = null
}

variable "network_excludes" {
  description = "(optional) - The zones to exclude"
  type        = list(string)
  default     = null
}

variable "network_includes" {
  description = "(optional) - The zones to include"
  type        = list(string)
  default     = null
}

variable "policyid" {
  description = "(required) - Policy ID of the Rule"
  type        = string
}

variable "priority" {
  description = "(optional) - Policy Rule Priority, this attribute can be set to a valid priority. To avoid endless diff situation we error if an invalid priority is provided. API defaults it to the last (lowest) if not there."
  type        = number
  default     = null
}

variable "session_idle" {
  description = "(optional) - Max minutes a session can be idle."
  type        = number
  default     = null
}

variable "session_lifetime" {
  description = "(optional) - Max minutes a session is active: Disable = 0."
  type        = number
  default     = null
}

variable "session_persistent" {
  description = "(optional) - Whether session cookies will last across browser sessions. Okta Administrators can never have persistent session cookies."
  type        = bool
  default     = null
}

variable "status" {
  description = "(optional) - Policy Rule Status: ACTIVE or INACTIVE."
  type        = string
  default     = null
}

variable "users_excluded" {
  description = "(optional) - Set of User IDs to Exclude"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_policy_rule_signon" "this" {
  # access - (optional) is a type of string
  access = var.access
  # authtype - (optional) is a type of string
  authtype = var.authtype
  # mfa_lifetime - (optional) is a type of number
  mfa_lifetime = var.mfa_lifetime
  # mfa_prompt - (optional) is a type of string
  mfa_prompt = var.mfa_prompt
  # mfa_remember_device - (optional) is a type of bool
  mfa_remember_device = var.mfa_remember_device
  # mfa_required - (optional) is a type of bool
  mfa_required = var.mfa_required
  # name - (required) is a type of string
  name = var.name
  # network_connection - (optional) is a type of string
  network_connection = var.network_connection
  # network_excludes - (optional) is a type of list of string
  network_excludes = var.network_excludes
  # network_includes - (optional) is a type of list of string
  network_includes = var.network_includes
  # policyid - (required) is a type of string
  policyid = var.policyid
  # priority - (optional) is a type of number
  priority = var.priority
  # session_idle - (optional) is a type of number
  session_idle = var.session_idle
  # session_lifetime - (optional) is a type of number
  session_lifetime = var.session_lifetime
  # session_persistent - (optional) is a type of bool
  session_persistent = var.session_persistent
  # status - (optional) is a type of string
  status = var.status
  # users_excluded - (optional) is a type of set of string
  users_excluded = var.users_excluded
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_policy_rule_signon.this.id
}

output "this" {
  value = okta_policy_rule_signon.this
}
```

[top](#index)