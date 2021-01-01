# google_compute_node_types

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
module "google_compute_node_types" {
  source = "./modules/google/d/google_compute_node_types"

  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```hcl
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "google_compute_node_types" "this" {
  project = var.project
  zone    = var.zone
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.google_compute_node_types.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.google_compute_node_types.this.names
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_node_types.this.project
}

output "zone" {
  description = "returns a string"
  value       = data.google_compute_node_types.this.zone
}

output "this" {
  value = google_compute_node_types.this
}
```

[top](#index)