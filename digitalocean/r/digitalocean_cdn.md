# digitalocean_cdn

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
module "digitalocean_cdn" {
  source = "./modules/digitalocean/r/digitalocean_cdn"

  # certificate_id - (optional) is a type of string
  certificate_id = null
  # certificate_name - (optional) is a type of string
  certificate_name = null
  # custom_domain - (optional) is a type of string
  custom_domain = null
  # origin - (required) is a type of string
  origin = null
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(optional) - ID of a DigitalOcean managed TLS certificate for use with custom domains"
  type        = string
  default     = null
}

variable "certificate_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "custom_domain" {
  description = "(optional) - fully qualified domain name (FQDN) for custom subdomain, (requires certificate_id)"
  type        = string
  default     = null
}

variable "origin" {
  description = "(required) - fully qualified domain name (FQDN) for the origin server"
  type        = string
}

variable "ttl" {
  description = "(optional) - The amount of time the content is cached in the CDN"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_cdn" "this" {
  # certificate_id - (optional) is a type of string
  certificate_id = var.certificate_id
  # certificate_name - (optional) is a type of string
  certificate_name = var.certificate_name
  # custom_domain - (optional) is a type of string
  custom_domain = var.custom_domain
  # origin - (required) is a type of string
  origin = var.origin
  # ttl - (optional) is a type of number
  ttl = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "certificate_id" {
  description = "returns a string"
  value       = digitalocean_cdn.this.certificate_id
}

output "certificate_name" {
  description = "returns a string"
  value       = digitalocean_cdn.this.certificate_name
}

output "created_at" {
  description = "returns a string"
  value       = digitalocean_cdn.this.created_at
}

output "endpoint" {
  description = "returns a string"
  value       = digitalocean_cdn.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = digitalocean_cdn.this.id
}

output "ttl" {
  description = "returns a number"
  value       = digitalocean_cdn.this.ttl
}

output "this" {
  value = digitalocean_cdn.this
}
```

[top](#index)