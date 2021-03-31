# digitalocean_droplet_snapshot

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
module "digitalocean_droplet_snapshot" {
  source = "./modules/digitalocean/r/digitalocean_droplet_snapshot"

  # droplet_id - (required) is a type of string
  droplet_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "droplet_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_droplet_snapshot" "this" {
  droplet_id = var.droplet_id
  name       = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = digitalocean_droplet_snapshot.this.created_at
}

output "id" {
  description = "returns a string"
  value       = digitalocean_droplet_snapshot.this.id
}

output "min_disk_size" {
  description = "returns a number"
  value       = digitalocean_droplet_snapshot.this.min_disk_size
}

output "regions" {
  description = "returns a set of string"
  value       = digitalocean_droplet_snapshot.this.regions
}

output "size" {
  description = "returns a number"
  value       = digitalocean_droplet_snapshot.this.size
}

output "this" {
  value = digitalocean_droplet_snapshot.this
}
```

[top](#index)