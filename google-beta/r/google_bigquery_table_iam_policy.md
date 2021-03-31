# google_bigquery_table_iam_policy

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
module "google_bigquery_table_iam_policy" {
  source = "./modules/google-beta/r/google_bigquery_table_iam_policy"

  # dataset_id - (required) is a type of string
  dataset_id = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
  # table_id - (required) is a type of string
  table_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dataset_id" {
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

variable "table_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_bigquery_table_iam_policy" "this" {
  dataset_id  = var.dataset_id
  policy_data = var.policy_data
  project     = var.project
  table_id    = var.table_id
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_bigquery_table_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_bigquery_table_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_bigquery_table_iam_policy.this.project
}

output "this" {
  value = google_bigquery_table_iam_policy.this
}
```

[top](#index)