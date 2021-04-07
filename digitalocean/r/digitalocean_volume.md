# digitalocean_volume

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
module "digitalocean_volume" {
  source = "./modules/digitalocean/r/digitalocean_volume"

  # description - (optional) is a type of string
  description = null
  # filesystem_type - (optional) is a type of string
  filesystem_type = null
  # initial_filesystem_label - (optional) is a type of string
  initial_filesystem_label = null
  # initial_filesystem_type - (optional) is a type of string
  initial_filesystem_type = null
  # name - (required) is a type of string
  name = null
  # region - (required) is a type of string
  region = null
  # size - (required) is a type of number
  size = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filesystem_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "initial_filesystem_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "initial_filesystem_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(required)"
  type        = number
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_volume" "this" {
  # description - (optional) is a type of string
  description = var.description
  # filesystem_type - (optional) is a type of string
  filesystem_type = var.filesystem_type
  # initial_filesystem_label - (optional) is a type of string
  initial_filesystem_label = var.initial_filesystem_label
  # initial_filesystem_type - (optional) is a type of string
  initial_filesystem_type = var.initial_filesystem_type
  # name - (required) is a type of string
  name = var.name
  # region - (required) is a type of string
  region = var.region
  # size - (required) is a type of number
  size = var.size
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # tags - (optional) is a type of set of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "droplet_ids" {
  description = "returns a set of number"
  value       = digitalocean_volume.this.droplet_ids
}

output "filesystem_label" {
  description = "returns a string"
  value       = digitalocean_volume.this.filesystem_label
}

output "filesystem_type" {
  description = "returns a string"
  value       = digitalocean_volume.this.filesystem_type
}

output "id" {
  description = "returns a string"
  value       = digitalocean_volume.this.id
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_volume.this.urn
}

output "this" {
  value = digitalocean_volume.this
}
```

[top](#index)