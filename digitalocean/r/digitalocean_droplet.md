# digitalocean_droplet

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_droplet" {
  source = "./modules/digitalocean/r/digitalocean_droplet"

  # backups - (optional) is a type of bool
  backups = null
  # image - (required) is a type of string
  image = null
  # ipv6 - (optional) is a type of bool
  ipv6 = null
  # monitoring - (optional) is a type of bool
  monitoring = null
  # name - (required) is a type of string
  name = null
  # private_networking - (optional) is a type of bool
  private_networking = null
  # region - (required) is a type of string
  region = null
  # resize_disk - (optional) is a type of bool
  resize_disk = null
  # size - (required) is a type of string
  size = null
  # ssh_keys - (optional) is a type of set of string
  ssh_keys = []
  # tags - (optional) is a type of set of string
  tags = []
  # user_data - (optional) is a type of string
  user_data = null
  # volume_ids - (optional) is a type of set of string
  volume_ids = []
  # vpc_uuid - (optional) is a type of string
  vpc_uuid = null
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

variable "image" {
  description = "(required)"
  type        = string
}

variable "ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "monitoring" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "private_networking" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "resize_disk" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "size" {
  description = "(required)"
  type        = string
}

variable "ssh_keys" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "vpc_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_droplet" "this" {
  # backups - (optional) is a type of bool
  backups = var.backups
  # image - (required) is a type of string
  image = var.image
  # ipv6 - (optional) is a type of bool
  ipv6 = var.ipv6
  # monitoring - (optional) is a type of bool
  monitoring = var.monitoring
  # name - (required) is a type of string
  name = var.name
  # private_networking - (optional) is a type of bool
  private_networking = var.private_networking
  # region - (required) is a type of string
  region = var.region
  # resize_disk - (optional) is a type of bool
  resize_disk = var.resize_disk
  # size - (required) is a type of string
  size = var.size
  # ssh_keys - (optional) is a type of set of string
  ssh_keys = var.ssh_keys
  # tags - (optional) is a type of set of string
  tags = var.tags
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # volume_ids - (optional) is a type of set of string
  volume_ids = var.volume_ids
  # vpc_uuid - (optional) is a type of string
  vpc_uuid = var.vpc_uuid
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = digitalocean_droplet.this.created_at
}

output "disk" {
  description = "returns a number"
  value       = digitalocean_droplet.this.disk
}

output "id" {
  description = "returns a string"
  value       = digitalocean_droplet.this.id
}

output "ipv4_address" {
  description = "returns a string"
  value       = digitalocean_droplet.this.ipv4_address
}

output "ipv4_address_private" {
  description = "returns a string"
  value       = digitalocean_droplet.this.ipv4_address_private
}

output "ipv6_address" {
  description = "returns a string"
  value       = digitalocean_droplet.this.ipv6_address
}

output "locked" {
  description = "returns a bool"
  value       = digitalocean_droplet.this.locked
}

output "memory" {
  description = "returns a number"
  value       = digitalocean_droplet.this.memory
}

output "price_hourly" {
  description = "returns a number"
  value       = digitalocean_droplet.this.price_hourly
}

output "price_monthly" {
  description = "returns a number"
  value       = digitalocean_droplet.this.price_monthly
}

output "private_networking" {
  description = "returns a bool"
  value       = digitalocean_droplet.this.private_networking
}

output "status" {
  description = "returns a string"
  value       = digitalocean_droplet.this.status
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_droplet.this.urn
}

output "vcpus" {
  description = "returns a number"
  value       = digitalocean_droplet.this.vcpus
}

output "volume_ids" {
  description = "returns a set of string"
  value       = digitalocean_droplet.this.volume_ids
}

output "vpc_uuid" {
  description = "returns a string"
  value       = digitalocean_droplet.this.vpc_uuid
}

output "this" {
  value = digitalocean_droplet.this
}
```

[top](#index)