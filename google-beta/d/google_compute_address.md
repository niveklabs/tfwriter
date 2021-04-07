# google_compute_address

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_address" {
  source = "./modules/google-beta/d/google_compute_address"

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
data "google_compute_address" "this" {
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.google_compute_address.this.address
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_address.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_address.this.project
}

output "region" {
  description = "returns a string"
  value       = data.google_compute_address.this.region
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_address.this.self_link
}

output "status" {
  description = "returns a string"
  value       = data.google_compute_address.this.status
}

output "this" {
  value = google_compute_address.this
}
```

[top](#index)