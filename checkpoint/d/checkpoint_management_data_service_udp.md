# checkpoint_management_data_service_udp

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_data_service_udp" {
  source = "./modules/checkpoint/d/checkpoint_management_data_service_udp"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Object name. Should be unique in the domain."
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
data "checkpoint_management_data_service_udp" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "accept_replies" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.accept_replies
}

output "aggressive_aging" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_service_udp.this.aggressive_aging
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_udp.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_udp.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_udp.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_udp.this.id
}

output "keep_connections_open_after_policy_installation" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.keep_connections_open_after_policy_installation
}

output "match_by_protocol_signature" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.match_by_protocol_signature
}

output "match_for_any" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.match_for_any
}

output "override_default_settings" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.override_default_settings
}

output "port" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_udp.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_udp.this.protocol
}

output "session_timeout" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_udp.this.session_timeout
}

output "source_port" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_udp.this.source_port
}

output "sync_connections_on_cluster" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.sync_connections_on_cluster
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_udp.this.tags
}

output "use_default_session_timeout" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_udp.this.use_default_session_timeout
}

output "this" {
  value = checkpoint_management_data_service_udp.this
}
```

[top](#index)