# google_compute_global_address

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_compute_global_address" {
  source = "./modules/google/d/google_compute_global_address"

  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
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

```hcl
data "google_compute_global_address" "this" {
  name    = var.name
  project = var.project
}
```

[top](#index)

### Outputs

```hcl
output "address" {
  description = "returns a string"
  value       = data.google_compute_global_address.this.address
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_global_address.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_global_address.this.project
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_global_address.this.self_link
}

output "status" {
  description = "returns a string"
  value       = data.google_compute_global_address.this.status
}

output "this" {
  value = google_compute_global_address.this
}
```

[top](#index)