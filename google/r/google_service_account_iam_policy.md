# google_service_account_iam_policy

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
module "google_service_account_iam_policy" {
  source = "./modules/google/r/google_service_account_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # service_account_id - (required) is a type of string
  service_account_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_data" {
  description = "(required)"
  type        = string
}

variable "service_account_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_service_account_iam_policy" "this" {
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
  # service_account_id - (required) is a type of string
  service_account_id = var.service_account_id
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_service_account_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_service_account_iam_policy.this.id
}

output "this" {
  value = google_service_account_iam_policy.this
}
```

[top](#index)