# hcloud_server

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_server" {
  source = "./modules/hcloud/d/hcloud_server"

  # name - (optional) is a type of string
  name = null
  # selector - (optional) is a type of string
  selector = null
  # with_selector - (optional) is a type of string
  with_selector = null
  # with_status - (optional) is a type of list of string
  with_status = []
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_status" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_server" "this" {
  name          = var.name
  selector      = var.selector
  with_selector = var.with_selector
  with_status   = var.with_status
}
```

[top](#index)

### Outputs

```terraform
output "backup_window" {
  description = "returns a string"
  value       = data.hcloud_server.this.backup_window
}

output "backups" {
  description = "returns a bool"
  value       = data.hcloud_server.this.backups
}

output "datacenter" {
  description = "returns a string"
  value       = data.hcloud_server.this.datacenter
}

output "firewall_ids" {
  description = "returns a list of number"
  value       = data.hcloud_server.this.firewall_ids
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_server.this.id
}

output "image" {
  description = "returns a string"
  value       = data.hcloud_server.this.image
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.hcloud_server.this.ipv4_address
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.hcloud_server.this.ipv6_address
}

output "ipv6_network" {
  description = "returns a string"
  value       = data.hcloud_server.this.ipv6_network
}

output "iso" {
  description = "returns a string"
  value       = data.hcloud_server.this.iso
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_server.this.labels
}

output "location" {
  description = "returns a string"
  value       = data.hcloud_server.this.location
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_server.this.name
}

output "rescue" {
  description = "returns a string"
  value       = data.hcloud_server.this.rescue
}

output "server_type" {
  description = "returns a string"
  value       = data.hcloud_server.this.server_type
}

output "status" {
  description = "returns a string"
  value       = data.hcloud_server.this.status
}

output "this" {
  value = hcloud_server.this
}
```

[top](#index)