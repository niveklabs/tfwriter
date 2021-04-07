# google_healthcare_dataset_iam_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_healthcare_dataset_iam_policy" {
  source = "./modules/google/r/google_healthcare_dataset_iam_policy"

  # dataset_id - (required) is a type of string
  dataset_id = null
  # policy_data - (required) is a type of string
  policy_data = null
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
```

[top](#index)

### Resource

```terraform
resource "google_healthcare_dataset_iam_policy" "this" {
  # dataset_id - (required) is a type of string
  dataset_id = var.dataset_id
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_healthcare_dataset_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_healthcare_dataset_iam_policy.this.id
}

output "this" {
  value = google_healthcare_dataset_iam_policy.this
}
```

[top](#index)