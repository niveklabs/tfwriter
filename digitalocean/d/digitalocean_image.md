# digitalocean_image

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
module "digitalocean_image" {
  source = null

  # name - (optional) is a type of string
  name = null
  # slug - (optional) is a type of string
  slug = null
  # source - (optional) is a type of string
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - name of the image"
  type        = string
  default     = null
}

variable "slug" {
  description = "(optional) - slug of the image"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_image" "this" {
  name   = var.name
  slug   = var.slug
  source = var.source
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.digitalocean_image.this.created
}

output "description" {
  description = "returns a string"
  value       = data.digitalocean_image.this.description
}

output "distribution" {
  description = "returns a string"
  value       = data.digitalocean_image.this.distribution
}

output "error_message" {
  description = "returns a string"
  value       = data.digitalocean_image.this.error_message
}

output "id" {
  description = "returns a number"
  value       = data.digitalocean_image.this.id
}

output "image" {
  description = "returns a string"
  value       = data.digitalocean_image.this.image
}

output "min_disk_size" {
  description = "returns a number"
  value       = data.digitalocean_image.this.min_disk_size
}

output "name" {
  description = "returns a string"
  value       = data.digitalocean_image.this.name
}

output "private" {
  description = "returns a bool"
  value       = data.digitalocean_image.this.private
}

output "regions" {
  description = "returns a set of string"
  value       = data.digitalocean_image.this.regions
}

output "size_gigabytes" {
  description = "returns a number"
  value       = data.digitalocean_image.this.size_gigabytes
}

output "slug" {
  description = "returns a string"
  value       = data.digitalocean_image.this.slug
}

output "status" {
  description = "returns a string"
  value       = data.digitalocean_image.this.status
}

output "tags" {
  description = "returns a set of string"
  value       = data.digitalocean_image.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.digitalocean_image.this.type
}

output "this" {
  value = digitalocean_image.this
}
```

[top](#index)