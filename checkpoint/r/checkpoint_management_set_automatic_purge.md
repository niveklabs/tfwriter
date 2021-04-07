# checkpoint_management_set_automatic_purge

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_set_automatic_purge" {
  source = "./modules/checkpoint/r/checkpoint_management_set_automatic_purge"

  # enabled - (required) is a type of bool
  enabled = null
  # keep_sessions_by_count - (optional) is a type of bool
  keep_sessions_by_count = null
  # keep_sessions_by_days - (optional) is a type of bool
  keep_sessions_by_days = null
  # number_of_days_to_keep - (optional) is a type of number
  number_of_days_to_keep = null
  # number_of_sessions_to_keep - (optional) is a type of number
  number_of_sessions_to_keep = null
  # scheduling - (optional) is a type of map of string
  scheduling = {}
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required) - Turn on/off the automatic-purge feature."
  type        = bool
}

variable "keep_sessions_by_count" {
  description = "(optional) - Whether or not to keep the latest N sessions. Note: when the automatic purge feature is enabled, this field and/or the \"keep-sessions-by-date\" field must be set to 'true'."
  type        = bool
  default     = null
}

variable "keep_sessions_by_days" {
  description = "(optional) - Whether or not to keep the sessions for D days. Note: when the automatic purge feature is enabled, this field and/or the \"keep-sessions-by-count\" field must be set to 'true'."
  type        = bool
  default     = null
}

variable "number_of_days_to_keep" {
  description = "(optional) - When \"keep-sessions-by-days = true\" this sets the number of days to keep the sessions."
  type        = number
  default     = null
}

variable "number_of_sessions_to_keep" {
  description = "(optional) - When \"keep-sessions-by-count = true\" this sets the number of newest sessions to preserve, by the sessions's publish date."
  type        = number
  default     = null
}

variable "scheduling" {
  description = "(optional) - When to purge sessions that do not meet the \"keep\" criteria. Note: when the automatic purge feature is enabled, this field must be set."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_set_automatic_purge" "this" {
  # enabled - (required) is a type of bool
  enabled = var.enabled
  # keep_sessions_by_count - (optional) is a type of bool
  keep_sessions_by_count = var.keep_sessions_by_count
  # keep_sessions_by_days - (optional) is a type of bool
  keep_sessions_by_days = var.keep_sessions_by_days
  # number_of_days_to_keep - (optional) is a type of number
  number_of_days_to_keep = var.number_of_days_to_keep
  # number_of_sessions_to_keep - (optional) is a type of number
  number_of_sessions_to_keep = var.number_of_sessions_to_keep
  # scheduling - (optional) is a type of map of string
  scheduling = var.scheduling
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_set_automatic_purge.this.id
}

output "this" {
  value = checkpoint_management_set_automatic_purge.this
}
```

[top](#index)