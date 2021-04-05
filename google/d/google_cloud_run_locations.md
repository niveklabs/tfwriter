# google_cloud_run_locations

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
module "google_cloud_run_locations" {
  source = "./modules/google/d/google_cloud_run_locations"

  # project - (optional) is a type of string
  project = null
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
```

[top](#index)

### Datasource

```terraform
data "google_cloud_run_locations" "this" {
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_cloud_run_locations.this.id
}

output "locations" {
  description = "returns a list of string"
  value       = data.google_cloud_run_locations.this.locations
}

output "project" {
  description = "returns a string"
  value       = data.google_cloud_run_locations.this.project
}

output "this" {
  value = google_cloud_run_locations.this
}
```

[top](#index)