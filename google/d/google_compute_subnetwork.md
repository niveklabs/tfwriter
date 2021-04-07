# google_compute_subnetwork

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
module "google_compute_subnetwork" {
  source = "./modules/google/d/google_compute_subnetwork"

  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # self_link - (optional) is a type of string
  self_link = null
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

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "self_link" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_subnetwork" "this" {
  # name - (optional) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # self_link - (optional) is a type of string
  self_link = var.self_link
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.description
}

output "gateway_address" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.gateway_address
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.id
}

output "ip_cidr_range" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.ip_cidr_range
}

output "network" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.network
}

output "private_ip_google_access" {
  description = "returns a bool"
  value       = data.google_compute_subnetwork.this.private_ip_google_access
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.project
}

output "region" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.region
}

output "secondary_ip_range" {
  description = "returns a list of object"
  value       = data.google_compute_subnetwork.this.secondary_ip_range
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_subnetwork.this.self_link
}

output "this" {
  value = google_compute_subnetwork.this
}
```

[top](#index)