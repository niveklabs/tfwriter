# google_data_catalog_taxonomy_iam_policy

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_data_catalog_taxonomy_iam_policy" {
  source = "./modules/google-beta/r/google_data_catalog_taxonomy_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # taxonomy - (required) is a type of string
  taxonomy = null
}
```

[top](#index)

### Variables

```terraform
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

variable "taxonomy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_data_catalog_taxonomy_iam_policy" "this" {
  policy_data = var.policy_data
  project     = var.project
  region      = var.region
  taxonomy    = var.taxonomy
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_policy.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_catalog_taxonomy_iam_policy.this.region
}

output "this" {
  value = google_data_catalog_taxonomy_iam_policy.this
}
```

[top](#index)