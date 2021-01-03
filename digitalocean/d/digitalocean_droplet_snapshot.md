# digitalocean_droplet_snapshot

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
    digitalocean = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_droplet_snapshot" {
  source = "./modules/digitalocean/d/digitalocean_droplet_snapshot"

  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_droplet_snapshot" "this" {
  most_recent = var.most_recent
  name        = var.name
  name_regex  = var.name_regex
  region      = var.region
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_droplet_snapshot.this.created_at
}

output "droplet_id" {
  description = "returns a string"
  value       = data.digitalocean_droplet_snapshot.this.droplet_id
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_droplet_snapshot.this.id
}

output "min_disk_size" {
  description = "returns a number"
  value       = data.digitalocean_droplet_snapshot.this.min_disk_size
}

output "regions" {
  description = "returns a set of string"
  value       = data.digitalocean_droplet_snapshot.this.regions
}

output "size" {
  description = "returns a number"
  value       = data.digitalocean_droplet_snapshot.this.size
}

output "this" {
  value = digitalocean_droplet_snapshot.this
}
```

[top](#index)