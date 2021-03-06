# checkpoint_management_data_service_other

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
module "checkpoint_management_data_service_other" {
  source = "./modules/checkpoint/d/checkpoint_management_data_service_other"

  # comments - (optional) is a type of string
  comments = null
  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "comments" {
  description = "(optional) - Comments string."
  type        = string
  default     = null
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
data "checkpoint_management_data_service_other" "this" {
  # comments - (optional) is a type of string
  comments = var.comments
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "accept_replies" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_other.this.accept_replies
}

output "action" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_other.this.action
}

output "aggressive_aging" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_service_other.this.aggressive_aging
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_other.this.color
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_other.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_other.this.id
}

output "ip_protocol" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_other.this.ip_protocol
}

output "keep_connections_open_after_policy_installation" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_other.this.keep_connections_open_after_policy_installation
}

output "match" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_other.this.match
}

output "match_for_any" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_other.this.match_for_any
}

output "override_default_settings" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_other.this.override_default_settings
}

output "session_timeout" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_other.this.session_timeout
}

output "sync_connections_on_cluster" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_other.this.sync_connections_on_cluster
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_other.this.tags
}

output "use_default_session_timeout" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_other.this.use_default_session_timeout
}

output "this" {
  value = checkpoint_management_data_service_other.this
}
```

[top](#index)