# digitalocean_region

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
module "digitalocean_region" {
  source = "./modules/digitalocean/d/digitalocean_region"

  # slug - (required) is a type of string
  slug = null
}
```

[top](#index)

### Variables

```terraform
variable "slug" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_region" "this" {
  # slug - (required) is a type of string
  slug = var.slug
}
```

[top](#index)

### Outputs

```terraform
output "available" {
  description = "returns a bool"
  value       = data.digitalocean_region.this.available
}

output "features" {
  description = "returns a set of string"
  value       = data.digitalocean_region.this.features
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_region.this.id
}

output "name" {
  description = "returns a string"
  value       = data.digitalocean_region.this.name
}

output "sizes" {
  description = "returns a set of string"
  value       = data.digitalocean_region.this.sizes
}

output "this" {
  value = digitalocean_region.this
}
```

[top](#index)