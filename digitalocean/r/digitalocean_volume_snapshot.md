# digitalocean_volume_snapshot

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
module "digitalocean_volume_snapshot" {
  source = "./modules/digitalocean/r/digitalocean_volume_snapshot"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of set of string
  tags = []
  # volume_id - (required) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "volume_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_volume_snapshot" "this" {
  name      = var.name
  tags      = var.tags
  volume_id = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = digitalocean_volume_snapshot.this.created_at
}

output "id" {
  description = "returns a string"
  value       = digitalocean_volume_snapshot.this.id
}

output "min_disk_size" {
  description = "returns a number"
  value       = digitalocean_volume_snapshot.this.min_disk_size
}

output "regions" {
  description = "returns a set of string"
  value       = digitalocean_volume_snapshot.this.regions
}

output "size" {
  description = "returns a number"
  value       = digitalocean_volume_snapshot.this.size
}

output "this" {
  value = digitalocean_volume_snapshot.this
}
```

[top](#index)