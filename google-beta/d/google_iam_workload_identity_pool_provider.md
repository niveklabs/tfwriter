# google_iam_workload_identity_pool_provider

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
module "google_iam_workload_identity_pool_provider" {
  source = "./modules/google-beta/d/google_iam_workload_identity_pool_provider"

  # project - (optional) is a type of string
  project = null
  # workload_identity_pool_id - (required) is a type of string
  workload_identity_pool_id = null
  # workload_identity_pool_provider_id - (required) is a type of string
  workload_identity_pool_provider_id = null
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
  description = "(required) - The ID used for the pool, which is the final component of the pool resource name. This\nvalue should be 4-32 characters, and may contain the characters [a-z0-9-]. The prefix\n'gcp-' is reserved for use by Google, and may not be specified."
  type        = string
}

variable "workload_identity_pool_provider_id" {
  description = "(required) - The ID for the provider, which becomes the final component of the resource name. This\nvalue must be 4-32 characters, and may contain the characters [a-z0-9-]. The prefix\n'gcp-' is reserved for use by Google, and may not be specified."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_iam_workload_identity_pool_provider" "this" {
  # project - (optional) is a type of string
  project = var.project
  # workload_identity_pool_id - (required) is a type of string
  workload_identity_pool_id = var.workload_identity_pool_id
  # workload_identity_pool_provider_id - (required) is a type of string
  workload_identity_pool_provider_id = var.workload_identity_pool_provider_id
}
```

[top](#index)

### Outputs

```terraform
output "attribute_condition" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool_provider.this.attribute_condition
}

output "attribute_mapping" {
  description = "returns a map of string"
  value       = data.google_iam_workload_identity_pool_provider.this.attribute_mapping
}

output "aws" {
  description = "returns a list of object"
  value       = data.google_iam_workload_identity_pool_provider.this.aws
}

output "description" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool_provider.this.description
}

output "disabled" {
  description = "returns a bool"
  value       = data.google_iam_workload_identity_pool_provider.this.disabled
}

output "display_name" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool_provider.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool_provider.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool_provider.this.name
}

output "oidc" {
  description = "returns a list of object"
  value       = data.google_iam_workload_identity_pool_provider.this.oidc
}

output "state" {
  description = "returns a string"
  value       = data.google_iam_workload_identity_pool_provider.this.state
}

output "this" {
  value = google_iam_workload_identity_pool_provider.this
}
```

[top](#index)