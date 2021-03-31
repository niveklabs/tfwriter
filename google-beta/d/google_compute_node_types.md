# google_compute_node_types

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_node_types" {
  source = "./modules/google-beta/d/google_compute_node_types"

  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
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

```terraform
data "google_compute_node_types" "this" {
  project = var.project
  zone    = var.zone
}
```

[top](#index)

### Outputs

```terraform
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