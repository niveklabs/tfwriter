# google_iam_workload_identity_pool

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
module "google_iam_workload_identity_pool" {
  source = "./modules/google-beta/d/google_iam_workload_identity_pool"

  # project - (optional) is a type of string
  project = null
  # workload_identity_pool_id - (required) is a type of string
  workload_identity_pool_id = null
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

variable "workload_identity_pool_id" {
  description = "(required) - The ID to use for the pool, which becomes the final component of the resource name. This\nvalue should be 4-32 characters, and may contain the characters [a-z0-9-]. The prefix\n'gcp-' is reserved for use by Google, and may not be specified."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_iam_workload_identity_pool" "this" {
  project                   = var.project
  workload_identity_pool_id = var.workload_identity_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool.this.description
}

output "disabled" {
  description = "returns a bool"
  value       = data.google_iam_workload_identity_pool.this.disabled
}

output "display_name" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool.this.name
}

output "state" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool.this.state
}

output "this" {
  value = google_iam_workload_identity_pool.this
}
```

[top](#index)