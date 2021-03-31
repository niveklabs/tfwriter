# google_healthcare_fhir_store_iam_policy

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
module "google_healthcare_fhir_store_iam_policy" {
  source = "./modules/google-beta/r/google_healthcare_fhir_store_iam_policy"

  # fhir_store_id - (required) is a type of string
  fhir_store_id = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "fhir_store_id" {
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
resource "google_healthcare_fhir_store_iam_policy" "this" {
  fhir_store_id = var.fhir_store_id
  policy_data   = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_healthcare_fhir_store_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_healthcare_fhir_store_iam_policy.this.id
}

output "this" {
  value = google_healthcare_fhir_store_iam_policy.this
}
```

[top](#index)