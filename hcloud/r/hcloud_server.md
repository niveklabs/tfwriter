# hcloud_server

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_server" {
  source = "./modules/hcloud/r/hcloud_server"

  # backups - (optional) is a type of bool
  backups = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # image - (required) is a type of string
  image = null
  # iso - (optional) is a type of string
  iso = null
  # keep_disk - (optional) is a type of bool
  keep_disk = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # rescue - (optional) is a type of string
  rescue = null
  # server_type - (required) is a type of string
  server_type = null
  # ssh_keys - (optional) is a type of list of string
  ssh_keys = []
  # user_data - (optional) is a type of string
  user_data = null
}
```

[top](#index)

### Variables

```terraform
variable "backups" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "datacenter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image" {
  description = "(required)"
  type        = string
}

variable "iso" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keep_disk" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rescue" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_type" {
  description = "(required)"
  type        = string
}

variable "ssh_keys" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_server" "this" {
  backups     = var.backups
  datacenter  = var.datacenter
  image       = var.image
  iso         = var.iso
  keep_disk   = var.keep_disk
  labels      = var.labels
  location    = var.location
  name        = var.name
  rescue      = var.rescue
  server_type = var.server_type
  ssh_keys    = var.ssh_keys
  user_data   = var.user_data
}
```

[top](#index)

### Outputs

```terraform
output "backup_window" {
  description = "returns a string"
  value       = hcloud_server.this.backup_window
}

output "datacenter" {
  description = "returns a string"
  value       = hcloud_server.this.datacenter
}

output "id" {
  description = "returns a string"
  value       = hcloud_server.this.id
}

output "ipv4_address" {
  description = "returns a string"
  value       = hcloud_server.this.ipv4_address
}

output "ipv6_address" {
  description = "returns a string"
  value       = hcloud_server.this.ipv6_address
}

output "ipv6_network" {
  description = "returns a string"
  value       = hcloud_server.this.ipv6_network
}

output "location" {
  description = "returns a string"
  value       = hcloud_server.this.location
}

output "status" {
  description = "returns a string"
  value       = hcloud_server.this.status
}

output "this" {
  value = hcloud_server.this
}
```

[top](#index)