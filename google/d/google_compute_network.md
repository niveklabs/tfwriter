# google_compute_network

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_network" {
  source = "./modules/google/d/google_compute_network"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_network" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_compute_network.this.description
}

output "gateway_ipv4" {
  description = "returns a string"
  value       = data.google_compute_network.this.gateway_ipv4
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_network.this.id
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_network.this.self_link
}

output "subnetworks_self_links" {
  description = "returns a list of string"
  value       = data.google_compute_network.this.subnetworks_self_links
}

output "this" {
  value = google_compute_network.this
}
```

[top](#index)