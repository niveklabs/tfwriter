# checkpoint_management_checkpoint_host

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
module "checkpoint_management_checkpoint_host" {
  source = "./modules/checkpoint/d/checkpoint_management_checkpoint_host"

  # management_blades - (optional) is a type of map of string
  management_blades = {}
  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "management_blades" {
  description = "(optional) - Management blades."
  type        = map(string)
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
data "checkpoint_management_checkpoint_host" "this" {
  management_blades = var.management_blades
  name              = var.name
  uid               = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.comments
}

output "hardware" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.hardware
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.id
}

output "interfaces" {
  description = "returns a list of object"
  value       = data.checkpoint_management_checkpoint_host.this.interfaces
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.ipv4_address
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.ipv6_address
}

output "logs_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_checkpoint_host.this.logs_settings
}

output "nat_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_checkpoint_host.this.nat_settings
}

output "os" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.os
}

output "save_logs_locally" {
  description = "returns a bool"
  value       = data.checkpoint_management_checkpoint_host.this.save_logs_locally
}

output "send_alerts_to_server" {
  description = "returns a set of string"
  value       = data.checkpoint_management_checkpoint_host.this.send_alerts_to_server
}

output "send_logs_to_backup_server" {
  description = "returns a set of string"
  value       = data.checkpoint_management_checkpoint_host.this.send_logs_to_backup_server
}

output "send_logs_to_server" {
  description = "returns a set of string"
  value       = data.checkpoint_management_checkpoint_host.this.send_logs_to_server
}

output "sic_name" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.sic_name
}

output "sic_state" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.sic_state
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_checkpoint_host.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.checkpoint_management_checkpoint_host.this.version
}

output "this" {
  value = checkpoint_management_checkpoint_host.this
}
```

[top](#index)