# okta_password_policy_rule

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
module "okta_password_policy_rule" {
  source = "./modules/okta/r/okta_password_policy_rule"

  # name - (required) is a type of string
  name = null
  # network_connection - (optional) is a type of string
  network_connection = null
  # network_excludes - (optional) is a type of list of string
  network_excludes = []
  # network_includes - (optional) is a type of list of string
  network_includes = []
  # password_change - (optional) is a type of string
  password_change = null
  # password_reset - (optional) is a type of string
  password_reset = null
  # password_unlock - (optional) is a type of string
  password_unlock = null
  # policyid - (required) is a type of string
  policyid = null
  # priority - (optional) is a type of number
  priority = null
  # status - (optional) is a type of string
  status = null
  # users_excluded - (optional) is a type of set of string
  users_excluded = []
}
```

[top](#index)

### Variables

```terraform
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

variable "password_change" {
  description = "(optional) - Allow or deny a user to change their password: ALLOW or DENY. Default = ALLOW"
  type        = string
  default     = null
}

variable "password_reset" {
  description = "(optional) - Allow or deny a user to reset their password: ALLOW or DENY. Default = ALLOW"
  type        = string
  default     = null
}

variable "password_unlock" {
  description = "(optional) - Allow or deny a user to unlock. Default = DENY"
  type        = string
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
resource "okta_password_policy_rule" "this" {
  name               = var.name
  network_connection = var.network_connection
  network_excludes   = var.network_excludes
  network_includes   = var.network_includes
  password_change    = var.password_change
  password_reset     = var.password_reset
  password_unlock    = var.password_unlock
  policyid           = var.policyid
  priority           = var.priority
  status             = var.status
  users_excluded     = var.users_excluded
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_password_policy_rule.this.id
}

output "this" {
  value = okta_password_policy_rule.this
}
```

[top](#index)