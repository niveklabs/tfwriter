# checkpoint_management_mds

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
module "checkpoint_management_mds" {
  source = "./modules/checkpoint/d/checkpoint_management_mds"

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
data "checkpoint_management_mds" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.comments
}

output "domains" {
  description = "returns a set of string"
  value       = data.checkpoint_management_mds.this.domains
}

output "global_domains" {
  description = "returns a set of string"
  value       = data.checkpoint_management_mds.this.global_domains
}

output "hardware" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.hardware
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.id
}

output "ip_pool_first" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.ip_pool_first
}

output "ip_pool_last" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.ip_pool_last
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.ipv4_address
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.ipv6_address
}

output "os" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.os
}

output "server_type" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.server_type
}

output "sic_name" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.sic_name
}

output "sic_state" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.sic_state
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_mds.this.tags
}

output "version" {
  description = "returns a string"
  value       = data.checkpoint_management_mds.this.version
}

output "this" {
  value = checkpoint_management_mds.this
}
```

[top](#index)