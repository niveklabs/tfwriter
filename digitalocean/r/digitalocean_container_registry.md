# digitalocean_container_registry

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
module "digitalocean_container_registry" {
  source = "./modules/digitalocean/r/digitalocean_container_registry"

  # name - (required) is a type of string
  name = null
  # subscription_tier_slug - (required) is a type of string
  subscription_tier_slug = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "subscription_tier_slug" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_container_registry" "this" {
  name                   = var.name
  subscription_tier_slug = var.subscription_tier_slug
}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = digitalocean_container_registry.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = digitalocean_container_registry.this.id
}

output "server_url" {
  description = "returns a string"
  value       = digitalocean_container_registry.this.server_url
}

output "this" {
  value = digitalocean_container_registry.this
}
```

[top](#index)