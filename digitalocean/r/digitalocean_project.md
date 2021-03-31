# digitalocean_project

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
module "digitalocean_project" {
  source = "./modules/digitalocean/r/digitalocean_project"

  # description - (optional) is a type of string
  description = null
  # environment - (optional) is a type of string
  environment = null
  # name - (required) is a type of string
  name = null
  # purpose - (optional) is a type of string
  purpose = null
  # resources - (optional) is a type of set of string
  resources = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - the description of the project"
  type        = string
  default     = null
}

variable "environment" {
  description = "(optional) - the environment of the project's resources"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - the human-readable name for the project"
  type        = string
}

variable "purpose" {
  description = "(optional) - the purpose of the project"
  type        = string
  default     = null
}

variable "resources" {
  description = "(optional) - the resources associated with the project"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "digitalocean_project" "this" {
  description = var.description
  environment = var.environment
  name        = var.name
  purpose     = var.purpose
  resources   = var.resources
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = digitalocean_project.this.created_at
}

output "id" {
  description = "returns a string"
  value       = digitalocean_project.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = digitalocean_project.this.is_default
}

output "owner_id" {
  description = "returns a number"
  value       = digitalocean_project.this.owner_id
}

output "owner_uuid" {
  description = "returns a string"
  value       = digitalocean_project.this.owner_uuid
}

output "resources" {
  description = "returns a set of string"
  value       = digitalocean_project.this.resources
}

output "updated_at" {
  description = "returns a string"
  value       = digitalocean_project.this.updated_at
}

output "this" {
  value = digitalocean_project.this
}
```

[top](#index)