# checkpoint_management_threat_rule

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
module "checkpoint_management_threat_rule" {
  source = "./modules/checkpoint/d/checkpoint_management_threat_rule"

  # layer - (required) is a type of string
  layer = null
  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "layer" {
  description = "(required) - Layer that the rule belongs to identified by the name or UID."
  type        = string
}

variable "name" {
  description = "(optional) - Rule name."
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
data "checkpoint_management_threat_rule" "this" {
  layer = var.layer
  name  = var.name
  uid   = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_rule.this.action
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_rule.this.comments
}

output "destination" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_rule.this.destination
}

output "destination_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_rule.this.destination_negate
}

output "enabled" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_rule.this.enabled
}

output "exceptions" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_rule.this.exceptions
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_rule.this.id
}

output "install_on" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_rule.this.install_on
}

output "protected_scope" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_rule.this.protected_scope
}

output "protected_scope_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_rule.this.protected_scope_negate
}

output "service" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_rule.this.service
}

output "service_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_rule.this.service_negate
}

output "source" {
  description = "returns a set of string"
  value       = data.checkpoint_management_threat_rule.this.source
}

output "source_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_threat_rule.this.source_negate
}

output "track" {
  description = "returns a string"
  value       = data.checkpoint_management_threat_rule.this.track
}

output "track_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_threat_rule.this.track_settings
}

output "this" {
  value = checkpoint_management_threat_rule.this
}
```

[top](#index)