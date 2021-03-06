# google_compute_zones

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
module "google_compute_zones" {
  source = "./modules/google-beta/d/google_compute_zones"

  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # status - (optional) is a type of string
  status = null
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

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_zones" "this" {
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_compute_zones.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.google_compute_zones.this.names
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_zones.this.project
}

output "this" {
  value = google_compute_zones.this
}
```

[top](#index)