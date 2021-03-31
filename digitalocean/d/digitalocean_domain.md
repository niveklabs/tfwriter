# digitalocean_domain

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
module "digitalocean_domain" {
  source = "./modules/digitalocean/d/digitalocean_domain"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of the domain"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "digitalocean_domain" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.digitalocean_domain.this.id
}

output "ttl" {
  description = "returns a number"
  value       = data.digitalocean_domain.this.ttl
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_domain.this.urn
}

output "zone_file" {
  description = "returns a string"
  value       = data.digitalocean_domain.this.zone_file
}

output "this" {
  value = digitalocean_domain.this
}
```

[top](#index)