# checkpoint_management_threat_exception

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
module "checkpoint_management_threat_exception" {
  source = []

  # action - (optional) is a type of string
  action = null
  # comments - (optional) is a type of string
  comments = null
  # destination - (optional) is a type of set of string
  destination = []
  # destination_negate - (optional) is a type of bool
  destination_negate = null
  # enabled - (optional) is a type of bool
  enabled = null
  # exception_group_name - (optional) is a type of string
  exception_group_name = null
  # exception_group_uid - (optional) is a type of string
  exception_group_uid = null
  # ignore_errors - (optional) is a type of bool
  ignore_errors = null
  # ignore_warnings - (optional) is a type of bool
  ignore_warnings = null
  # install_on - (optional) is a type of set of string
  install_on = []
  # layer - (required) is a type of string
  layer = null
  # name - (required) is a type of string
  name = null
  # position - (required) is a type of map of string
  position = {}
  # protected_scope - (optional) is a type of set of string
  protected_scope = []
  # protected_scope_negate - (optional) is a type of bool
  protected_scope_negate = null
  # protection_or_site - (optional) is a type of set of string
  protection_or_site = []
  # rule_name - (optional) is a type of string
  rule_name = null
  # rule_uid - (optional) is a type of string
  rule_uid = null
  # service - (optional) is a type of set of string
  service = []
  # service_negate - (optional) is a type of bool
  service_negate = null
  # source - (optional) is a type of set of string
  # source_negate - (optional) is a type of bool
  source_negate = null
  # track - (optional) is a type of string
  track = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional) - Action-the enforced profile."
  type        = string
  default     = null
}

variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
}

variable "destination" {
  description = "(optional) - Collection of Network objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "destination_negate" {
  description = "(optional) - True if negate is set for destination."
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - Enable/Disable the rule."
  type        = bool
  default     = null
}

variable "exception_group_name" {
  description = "(optional) - The name of the exception-group."
  type        = string
  default     = null
}

variable "exception_group_uid" {
  description = "(optional) - The UID of the exception-group."
  type        = string
  default     = null
}

variable "ignore_errors" {
  description = "(optional) - Apply changes ignoring errors. You won't be able to publish such a changes. If ignore-warnings flag was omitted - warnings will also be ignored."
  type        = bool
  default     = null
}

variable "ignore_warnings" {
  description = "(optional) - Apply changes ignoring warnings."
  type        = bool
  default     = null
}

variable "install_on" {
  description = "(optional) - Which Gateways identified by the name or UID to install the policy on."
  type        = set(string)
  default     = null
}

variable "layer" {
  description = "(required) - Layer that the rule belongs to identified by the name or UID."
  type        = string
}

variable "name" {
  description = "(required) - Rule name."
  type        = string
}

variable "position" {
  description = "(required) - Position in the rulebase."
  type        = map(string)
}

variable "protected_scope" {
  description = "(optional) - Collection of objects defining Protected Scope identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "protected_scope_negate" {
  description = "(optional) - True if negate is set for Protected Scope."
  type        = bool
  default     = null
}

variable "protection_or_site" {
  description = "(optional) - Name of the protection or site."
  type        = set(string)
  default     = null
}

variable "rule_name" {
  description = "(optional) - The name of the parent rule."
  type        = string
  default     = null
}

variable "rule_uid" {
  description = "(optional) - The UID of the parent rule."
  type        = string
  default     = null
}

variable "service" {
  description = "(optional) - Collection of Network objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "service_negate" {
  description = "(optional) - True if negate is set for service."
  type        = bool
  default     = null
}

variable "source" {
  description = "(optional) - Collection of Network objects identified by the name or UID."
  type        = set(string)
  default     = null
}

variable "source_negate" {
  description = "(optional) - True if negate is set for source."
  type        = bool
  default     = null
}

variable "track" {
  description = "(optional) - Packet tracking."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "checkpoint_management_threat_exception" "this" {
  action                 = var.action
  comments               = var.comments
  destination            = var.destination
  destination_negate     = var.destination_negate
  enabled                = var.enabled
  exception_group_name   = var.exception_group_name
  exception_group_uid    = var.exception_group_uid
  ignore_errors          = var.ignore_errors
  ignore_warnings        = var.ignore_warnings
  install_on             = var.install_on
  layer                  = var.layer
  name                   = var.name
  position               = var.position
  protected_scope        = var.protected_scope
  protected_scope_negate = var.protected_scope_negate
  protection_or_site     = var.protection_or_site
  rule_name              = var.rule_name
  rule_uid               = var.rule_uid
  service                = var.service
  service_negate         = var.service_negate
  source                 = var.source
  source_negate          = var.source_negate
  track                  = var.track
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = checkpoint_management_threat_exception.this.id
}

output "owner" {
  description = "returns a string"
  value       = checkpoint_management_threat_exception.this.owner
}

output "this" {
  value = checkpoint_management_threat_exception.this
}
```

[top](#index)