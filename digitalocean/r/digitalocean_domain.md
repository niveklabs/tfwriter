# digitalocean_domain

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
module "digitalocean_domain" {
  source = "./modules/digitalocean/r/digitalocean_domain"

  # ip_address - (optional) is a type of string
  ip_address = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_domain" "this" {
  # ip_address - (optional) is a type of string
  ip_address = var.ip_address
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = digitalocean_domain.this.id
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_domain.this.urn
}

output "this" {
  value = digitalocean_domain.this
}
```

[top](#index)