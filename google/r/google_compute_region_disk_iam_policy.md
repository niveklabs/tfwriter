# google_compute_region_disk_iam_policy

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
module "google_compute_region_disk_iam_policy" {
  source = "./modules/google/r/google_compute_region_disk_iam_policy"

  # name - (required) is a type of string
  name = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(required)"
  type        = string
}

variable "policy_data" {
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

### Resource

```hcl
resource "google_compute_region_disk_iam_policy" "this" {
  name        = var.name
  policy_data = var.policy_data
  project     = var.project
  region      = var.region
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = google_compute_region_disk_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_compute_region_disk_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_disk_iam_policy.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_disk_iam_policy.this.region
}

output "this" {
  value = google_compute_region_disk_iam_policy.this
}
```

[top](#index)