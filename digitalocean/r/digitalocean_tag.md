# digitalocean_tag

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
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_tag" {
  source = "./modules/digitalocean/r/digitalocean_tag"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_tag" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "databases_count" {
  description = "returns a number"
  value       = digitalocean_tag.this.databases_count
}

output "droplets_count" {
  description = "returns a number"
  value       = digitalocean_tag.this.droplets_count
}

output "id" {
  description = "returns a string"
  value       = digitalocean_tag.this.id
}

output "images_count" {
  description = "returns a number"
  value       = digitalocean_tag.this.images_count
}

output "total_resource_count" {
  description = "returns a number"
  value       = digitalocean_tag.this.total_resource_count
}

output "volume_snapshots_count" {
  description = "returns a number"
  value       = digitalocean_tag.this.volume_snapshots_count
}

output "volumes_count" {
  description = "returns a number"
  value       = digitalocean_tag.this.volumes_count
}

output "this" {
  value = digitalocean_tag.this
}
```

[top](#index)