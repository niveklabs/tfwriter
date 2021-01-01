# google_billing_account_iam_policy

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_billing_account_iam_policy" {
  source = "./modules/google/r/google_billing_account_iam_policy"

  # billing_account_id - (required) is a type of string
  billing_account_id = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```hcl
variable "billing_account_id" {
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
resource "google_billing_account_iam_policy" "this" {
  billing_account_id = var.billing_account_id
  policy_data        = var.policy_data
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = google_billing_account_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_billing_account_iam_policy.this.id
}

output "this" {
  value = google_billing_account_iam_policy.this
}
```

[top](#index)