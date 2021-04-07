# digitalocean_project

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
module "digitalocean_project" {
  source = "./modules/digitalocean/d/digitalocean_project"

  # name - (optional) is a type of string
  name = null
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
```

[top](#index)

### Datasource

```terraform
data "digitalocean_project" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.digitalocean_project.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.digitalocean_project.this.description
}

output "environment" {
  description = "returns a string"
  value       = data.digitalocean_project.this.environment
}

output "id" {
  description = "returns a string"
  value       = data.digitalocean_project.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = data.digitalocean_project.this.is_default
}

output "name" {
  description = "returns a string"
  value       = data.digitalocean_project.this.name
}

output "owner_id" {
  description = "returns a number"
  value       = data.digitalocean_project.this.owner_id
}

output "owner_uuid" {
  description = "returns a string"
  value       = data.digitalocean_project.this.owner_uuid
}

output "purpose" {
  description = "returns a string"
  value       = data.digitalocean_project.this.purpose
}

output "resources" {
  description = "returns a set of string"
  value       = data.digitalocean_project.this.resources
}

output "updated_at" {
  description = "returns a string"
  value       = data.digitalocean_project.this.updated_at
}

output "this" {
  value = digitalocean_project.this
}
```

[top](#index)