# google_kms_key_ring_iam_policy

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
module "google_kms_key_ring_iam_policy" {
  source = "./modules/google-beta/r/google_kms_key_ring_iam_policy"

  # key_ring_id - (required) is a type of string
  key_ring_id = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "key_ring_id" {
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
resource "google_kms_key_ring_iam_policy" "this" {
  key_ring_id = var.key_ring_id
  policy_data = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_kms_key_ring_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_kms_key_ring_iam_policy.this.id
}

output "this" {
  value = google_kms_key_ring_iam_policy.this
}
```

[top](#index)