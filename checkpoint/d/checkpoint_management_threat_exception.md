# checkpoint_management_threat_exception

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/checkpoint/d/checkpoint_management_threat_exception"

  # exception_group_name - (optional) is a type of string
  exception_group_name = null
  # exception_group_uid - (optional) is a type of string
  exception_group_uid = null
  # layer - (required) is a type of string
  layer = null
  # name - (optional) is a type of string
  name = null
  # rule_name - (optional) is a type of string
  rule_name = null
  # rule_uid - (optional) is a type of string
  rule_uid = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
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

variable "layer" {
  description = "(required) - Layer that the rule belongs to identified by the name or UID."
  type        = string
}

variable "name" {
  description = "(optional) - The name of the exception."
  type        = string
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

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_threat_exception" "this" {
  exception_group_name = var.exception_group_name
  exception_group_uid  = var.exception_group_uid
  layer                = var.layer
  name                 = var.name
  rule_name            = var.rule_name
  rule_uid             = var.rule_uid
  uid                  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_exception.this.action
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_exception.this.comments
}

output "destination" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_exception.this.destination
}

output "destination_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_exception.this.destination_negate
}

output "enabled" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_exception.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_exception.this.id
}

output "install_on" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_exception.this.install_on
}

output "owner" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_exception.this.owner
}

output "protected_scope" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_exception.this.protected_scope
}

output "protected_scope_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_exception.this.protected_scope_negate
}

output "protection_or_site" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_exception.this.protection_or_site
}

output "service" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_exception.this.service
}

output "service_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_exception.this.service_negate
}

output "source" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_exception.this.source
}

output "source_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_exception.this.source_negate
}

output "track" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_exception.this.track
}

output "this" {
  value = checkpoint_management_threat_exception.this
}
```

[top](#index)