# google_healthcare_consent_store_iam_policy

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_healthcare_consent_store_iam_policy" {
  source = "./modules/google/r/google_healthcare_consent_store_iam_policy"

  # consent_store_id - (required) is a type of string
  consent_store_id = null
  # dataset - (required) is a type of string
  dataset = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "consent_store_id" {
  description = "(required)"
  type        = string
}

variable "dataset" {
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
resource "google_healthcare_consent_store_iam_policy" "this" {
  consent_store_id = var.consent_store_id
  dataset          = var.dataset
  policy_data      = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_healthcare_consent_store_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_healthcare_consent_store_iam_policy.this.id
}

output "this" {
  value = google_healthcare_consent_store_iam_policy.this
}
```

[top](#index)