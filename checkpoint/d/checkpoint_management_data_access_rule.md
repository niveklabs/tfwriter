# checkpoint_management_data_access_rule

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
module "checkpoint_management_data_access_rule" {
  source = "./modules/checkpoint/d/checkpoint_management_data_access_rule"

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
  description = "(optional) - Object name."
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
data "checkpoint_management_data_access_rule" "this" {
  # layer - (required) is a type of string
  layer = var.layer
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_rule.this.action
}

output "action_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_access_rule.this.action_settings
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_rule.this.comments
}

output "content" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_rule.this.content
}

output "content_direction" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_rule.this.content_direction
}

output "content_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_rule.this.content_negate
}

output "custom_fields" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_access_rule.this.custom_fields
}

output "destination" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_rule.this.destination
}

output "destination_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_rule.this.destination_negate
}

output "enabled" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_rule.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_rule.this.id
}

output "inline_layer" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_rule.this.inline_layer
}

output "install_on" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_rule.this.install_on
}

output "service" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_rule.this.service
}

output "service_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_rule.this.service_negate
}

output "source" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_rule.this.source
}

output "source_negate" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_rule.this.source_negate
}

output "time" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_rule.this.time
}

output "track" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_access_rule.this.track
}

output "user_check" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_access_rule.this.user_check
}

output "vpn" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_rule.this.vpn
}

output "this" {
  value = checkpoint_management_data_access_rule.this
}
```

[top](#index)