# google_compute_vpn_gateway

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_vpn_gateway" {
  source = "./modules/google/d/google_compute_vpn_gateway"

  # name - (required) is a type of string
  name = null
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
  description = "(required)"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "google_compute_vpn_gateway" "this" {
  name    = var.name
  project = var.project
  region  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_compute_vpn_gateway.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_vpn_gateway.this.id
}

output "network" {
  description = "returns a string"
  value       = data.google_compute_vpn_gateway.this.network
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_vpn_gateway.this.project
}

output "region" {
  description = "returns a string"
  value       = data.google_compute_vpn_gateway.this.region
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_vpn_gateway.this.self_link
}

output "this" {
  value = google_compute_vpn_gateway.this
}
```

[top](#index)