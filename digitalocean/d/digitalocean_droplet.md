# digitalocean_droplet

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/digitalocean/d/digitalocean_droplet"

  # name - (optional) is a type of string
  name = null
  # tag - (optional) is a type of string
  tag = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - name of the Droplet"
  type        = string
  default     = null
}

variable "tag" {
  description = "(optional) - unique tag of the Droplet"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_droplet" "this" {
  name = var.name
  tag  = var.tag
}
```

[top](#index)

### Outputs

```terraform
output "backups" {
  description = "returns a bool"
  value       = data.digitalocean_droplet.this.backups
}

output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.created_at
}

output "disk" {
  description = "returns a number"
  value       = data.digitalocean_droplet.this.disk
}

output "id" {
  description = "returns a number"
  value       = data.digitalocean_droplet.this.id
}

output "image" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.image
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.ipv4_address
}

output "ipv4_address_private" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.ipv4_address_private
}

output "ipv6" {
  description = "returns a bool"
  value       = data.digitalocean_droplet.this.ipv6
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.ipv6_address
}

output "ipv6_address_private" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.ipv6_address_private
}

output "locked" {
  description = "returns a bool"
  value       = data.digitalocean_droplet.this.locked
}

output "memory" {
  description = "returns a number"
  value       = data.digitalocean_droplet.this.memory
}

output "monitoring" {
  description = "returns a bool"
  value       = data.digitalocean_droplet.this.monitoring
}

output "name" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.name
}

output "price_hourly" {
  description = "returns a number"
  value       = data.digitalocean_droplet.this.price_hourly
}

output "price_monthly" {
  description = "returns a number"
  value       = data.digitalocean_droplet.this.price_monthly
}

output "private_networking" {
  description = "returns a bool"
  value       = data.digitalocean_droplet.this.private_networking
}

output "region" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.region
}

output "size" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.size
}

output "status" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.status
}

output "tags" {
  description = "returns a set of string"
  value       = data.digitalocean_droplet.this.tags
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.urn
}

output "vcpus" {
  description = "returns a number"
  value       = data.digitalocean_droplet.this.vcpus
}

output "volume_ids" {
  description = "returns a set of string"
  value       = data.digitalocean_droplet.this.volume_ids
}

output "vpc_uuid" {
  description = "returns a string"
  value       = data.digitalocean_droplet.this.vpc_uuid
}

output "this" {
  value = digitalocean_droplet.this
}
```

[top](#index)