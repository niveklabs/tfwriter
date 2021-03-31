# google_storage_bucket_iam_policy

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
module "google_storage_bucket_iam_policy" {
  source = "./modules/google/r/google_storage_bucket_iam_policy"

  # bucket - (required) is a type of string
  bucket = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
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
resource "google_storage_bucket_iam_policy" "this" {
  bucket      = var.bucket
  policy_data = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_storage_bucket_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_storage_bucket_iam_policy.this.id
}

output "this" {
  value = google_storage_bucket_iam_policy.this
}
```

[top](#index)