# checkpoint_management_data_service_tcp

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
module "checkpoint_management_data_service_tcp" {
  source = "./modules/checkpoint/d/checkpoint_management_data_service_tcp"

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
data "checkpoint_management_data_service_tcp" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "aggressive_aging" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_service_tcp.this.aggressive_aging
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_tcp.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_tcp.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_tcp.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_tcp.this.id
}

output "keep_connections_open_after_policy_installation" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_tcp.this.keep_connections_open_after_policy_installation
}

output "match_by_protocol_signature" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_tcp.this.match_by_protocol_signature
}

output "match_for_any" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_tcp.this.match_for_any
}

output "override_default_settings" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_tcp.this.override_default_settings
}

output "port" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_tcp.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_tcp.this.protocol
}

output "session_timeout" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_tcp.this.session_timeout
}

output "source_port" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_tcp.this.source_port
}

output "sync_connections_on_cluster" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_tcp.this.sync_connections_on_cluster
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_tcp.this.tags
}

output "use_default_session_timeout" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_tcp.this.use_default_session_timeout
}

output "this" {
  value = checkpoint_management_data_service_tcp.this
}
```

[top](#index)