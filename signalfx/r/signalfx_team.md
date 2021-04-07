# signalfx_team

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_team" {
  source = "./modules/signalfx/r/signalfx_team"

  # description - (optional) is a type of string
  description = null
  # members - (optional) is a type of set of string
  members = []
  # name - (required) is a type of string
  name = null
  # notifications_critical - (optional) is a type of list of string
  notifications_critical = []
  # notifications_default - (optional) is a type of list of string
  notifications_default = []
  # notifications_info - (optional) is a type of list of string
  notifications_info = []
  # notifications_major - (optional) is a type of list of string
  notifications_major = []
  # notifications_minor - (optional) is a type of list of string
  notifications_minor = []
  # notifications_warning - (optional) is a type of list of string
  notifications_warning = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the team (Optional)"
  type        = string
  default     = null
}

variable "members" {
  description = "(optional) - Members of team"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the team"
  type        = string
}

variable "notifications_critical" {
  description = "(optional) - List of notification destinations to use for the critical alerts category."
  type        = list(string)
  default     = null
}

variable "notifications_default" {
  description = "(optional) - List of notification destinations to use for the default alerts category."
  type        = list(string)
  default     = null
}

variable "notifications_info" {
  description = "(optional) - List of notification destinations to use for the info alerts category."
  type        = list(string)
  default     = null
}

variable "notifications_major" {
  description = "(optional) - List of notification destinations to use for the major alerts category."
  type        = list(string)
  default     = null
}

variable "notifications_minor" {
  description = "(optional) - List of notification destinations to use for the minor alerts category."
  type        = list(string)
  default     = null
}

variable "notifications_warning" {
  description = "(optional) - List of notification destinations to use for the warning alerts category."
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_team" "this" {
  # description - (optional) is a type of string
  description = var.description
  # members - (optional) is a type of set of string
  members = var.members
  # name - (required) is a type of string
  name = var.name
  # notifications_critical - (optional) is a type of list of string
  notifications_critical = var.notifications_critical
  # notifications_default - (optional) is a type of list of string
  notifications_default = var.notifications_default
  # notifications_info - (optional) is a type of list of string
  notifications_info = var.notifications_info
  # notifications_major - (optional) is a type of list of string
  notifications_major = var.notifications_major
  # notifications_minor - (optional) is a type of list of string
  notifications_minor = var.notifications_minor
  # notifications_warning - (optional) is a type of list of string
  notifications_warning = var.notifications_warning
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = signalfx_team.this.id
}

output "url" {
  description = "returns a string"
  value       = signalfx_team.this.url
}

output "this" {
  value = signalfx_team.this
}
```

[top](#index)