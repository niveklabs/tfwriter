# okta_mfa_policy_rule

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
module "okta_mfa_policy_rule" {
  source = "./modules/okta/r/okta_mfa_policy_rule"

  # enroll - (optional) is a type of string
  enroll = null
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
  # status - (optional) is a type of string
  status = null
  # users_excluded - (optional) is a type of set of string
  users_excluded = []
}
```

[top](#index)

### Variables

```terraform
variable "enroll" {
  description = "(optional) - Should the user be enrolled the first time they LOGIN, the next time they are CHALLENGED, or NEVER?"
  type        = string
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
resource "okta_mfa_policy_rule" "this" {
  # enroll - (optional) is a type of string
  enroll = var.enroll
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
  value       = okta_mfa_policy_rule.this.id
}

output "this" {
  value = okta_mfa_policy_rule.this
}
```

[top](#index)