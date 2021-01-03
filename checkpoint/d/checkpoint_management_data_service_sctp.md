# checkpoint_management_data_service_sctp

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
module "checkpoint_management_data_service_sctp" {
  source = "./modules/checkpoint/d/checkpoint_management_data_service_sctp"

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
data "checkpoint_management_data_service_sctp" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "aggressive_aging" {
  description = "returns a map of string"
  value       = data.checkpoint_management_data_service_sctp.this.aggressive_aging
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_sctp.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_sctp.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_sctp.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_sctp.this.id
}

output "keep_connections_open_after_policy_installation" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_sctp.this.keep_connections_open_after_policy_installation
}

output "match_for_any" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_sctp.this.match_for_any
}

output "port" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_sctp.this.port
}

output "session_timeout" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_sctp.this.session_timeout
}

output "source_port" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_sctp.this.source_port
}

output "sync_connections_on_cluster" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_sctp.this.sync_connections_on_cluster
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_sctp.this.tags
}

output "use_default_session_timeout" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_sctp.this.use_default_session_timeout
}

output "this" {
  value = checkpoint_management_data_service_sctp.this
}
```

[top](#index)