# google_data_catalog_entry_group_iam_policy

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
module "google_data_catalog_entry_group_iam_policy" {
  source = "./modules/google-beta/r/google_data_catalog_entry_group_iam_policy"

  # entry_group - (required) is a type of string
  entry_group = null
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

```terraform
variable "entry_group" {
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

```terraform
resource "google_data_catalog_entry_group_iam_policy" "this" {
  entry_group = var.entry_group
  policy_data = var.policy_data
  project     = var.project
  region      = var.region
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_data_catalog_entry_group_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_data_catalog_entry_group_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_data_catalog_entry_group_iam_policy.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_catalog_entry_group_iam_policy.this.region
}

output "this" {
  value = google_data_catalog_entry_group_iam_policy.this
}
```

[top](#index)