# google_healthcare_hl7_v2_store_iam_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_healthcare_hl7_v2_store_iam_policy" {
  source = "./modules/google/r/google_healthcare_hl7_v2_store_iam_policy"

  # hl7_v2_store_id - (required) is a type of string
  hl7_v2_store_id = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```hcl
variable "hl7_v2_store_id" {
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

```hcl
resource "google_healthcare_hl7_v2_store_iam_policy" "this" {
  hl7_v2_store_id = var.hl7_v2_store_id
  policy_data     = var.policy_data
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = google_healthcare_hl7_v2_store_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_healthcare_hl7_v2_store_iam_policy.this.id
}

output "this" {
  value = google_healthcare_hl7_v2_store_iam_policy.this
}
```

[top](#index)