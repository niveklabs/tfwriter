# digitalocean_vpc

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
module "digitalocean_vpc" {
  source = "./modules/digitalocean/d/digitalocean_vpc"

  # name - (optional) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "digitalocean_vpc" "this" {
  name   = var.name
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.created_at
}

output "default" {
  description = "returns a bool"
  value       = data.digitalocean_vpc.this.default
}

output "description" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.description
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.id
}

output "ip_range" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.ip_range
}

output "name" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.name
}

output "region" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.region
}

output "urn" {
  description = "returns a string"
  value       = data.digitalocean_vpc.this.urn
}

output "this" {
  value = digitalocean_vpc.this
}
```

[top](#index)