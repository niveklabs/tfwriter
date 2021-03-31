# google_compute_region_instance_group

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
module "google_compute_region_instance_group" {
  source = "./modules/google/d/google_compute_region_instance_group"

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
data "google_compute_region_instance_group" "this" {
  name      = var.name
  project   = var.project
  region    = var.region
  self_link = var.self_link
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_compute_region_instance_group.this.id
}

output "instances" {
  description = "returns a list of object"
  value       = data.google_compute_region_instance_group.this.instances
}

output "name" {
  description = "returns a string"
  value       = data.google_compute_region_instance_group.this.name
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_region_instance_group.this.project
}

output "region" {
  description = "returns a string"
  value       = data.google_compute_region_instance_group.this.region
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_region_instance_group.this.self_link
}

output "size" {
  description = "returns a number"
  value       = data.google_compute_region_instance_group.this.size
}

output "this" {
  value = google_compute_region_instance_group.this
}
```

[top](#index)