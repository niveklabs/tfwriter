# google_compute_router

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_router" {
  source = "./modules/google/d/google_compute_router"

  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the resource. The name must be 1-63 characters long, and\ncomply with RFC1035. Specifically, the name must be 1-63 characters\nlong and match the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?'\nwhich means the first character must be a lowercase letter, and all\nfollowing characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(required) - A reference to the network to which this router belongs."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - Region where the router resides."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_router" "this" {
  # name - (required) is a type of string
  name = var.name
  # network - (required) is a type of string
  network = var.network
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "bgp" {
  description = "returns a list of object"
  value       = data.google_compute_router.this.bgp
}

output "creation_timestamp" {
  description = "returns a string"
  value       = data.google_compute_router.this.creation_timestamp
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_router.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_router.this.id
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_router.this.self_link
}

output "this" {
  value = google_compute_router.this
}
```

[top](#index)