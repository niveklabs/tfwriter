# digitalocean_custom_image

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
module "digitalocean_custom_image" {
  source = "./modules/digitalocean/r/digitalocean_custom_image"

  # description - (optional) is a type of string
  description = null
  # distribution - (optional) is a type of string
  distribution = null
  # name - (required) is a type of string
  name = null
  # regions - (required) is a type of list of string
  regions = []
  # tags - (optional) is a type of set of string
  tags = []
  # url - (required) is a type of string
  url = null
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

variable "distribution" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "regions" {
  description = "(required)"
  type        = list(string)
}

variable "tags" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_custom_image" "this" {
  description  = var.description
  distribution = var.distribution
  name         = var.name
  regions      = var.regions
  tags         = var.tags
  url          = var.url
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = digitalocean_custom_image.this.created_at
}

output "id" {
  description = "returns a string"
  value       = digitalocean_custom_image.this.id
}

output "image_id" {
  description = "returns a number"
  value       = digitalocean_custom_image.this.image_id
}

output "min_disk_size" {
  description = "returns a number"
  value       = digitalocean_custom_image.this.min_disk_size
}

output "public" {
  description = "returns a bool"
  value       = digitalocean_custom_image.this.public
}

output "size_gigabytes" {
  description = "returns a number"
  value       = digitalocean_custom_image.this.size_gigabytes
}

output "slug" {
  description = "returns a string"
  value       = digitalocean_custom_image.this.slug
}

output "status" {
  description = "returns a string"
  value       = digitalocean_custom_image.this.status
}

output "type" {
  description = "returns a string"
  value       = digitalocean_custom_image.this.type
}

output "this" {
  value = digitalocean_custom_image.this
}
```

[top](#index)