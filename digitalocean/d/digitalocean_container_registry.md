# digitalocean_container_registry

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
module "digitalocean_container_registry" {
  source = "./modules/digitalocean/d/digitalocean_container_registry"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of the container registry"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_container_registry" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = data.digitalocean_container_registry.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_container_registry.this.id
}

output "server_url" {
  description = "returns a string"
  value       = data.digitalocean_container_registry.this.server_url
}

output "subscription_tier_slug" {
  description = "returns a string"
  value       = data.digitalocean_container_registry.this.subscription_tier_slug
}

output "this" {
  value = digitalocean_container_registry.this
}
```

[top](#index)