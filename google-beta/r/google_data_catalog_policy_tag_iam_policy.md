# google_data_catalog_policy_tag_iam_policy

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
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_data_catalog_policy_tag_iam_policy" {
  source = "./modules/google-beta/r/google_data_catalog_policy_tag_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # policy_tag - (required) is a type of string
  policy_tag = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_data" {
  description = "(required)"
  type        = string
}

variable "policy_tag" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_data_catalog_policy_tag_iam_policy" "this" {
  policy_data = var.policy_data
  policy_tag  = var.policy_tag
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_data_catalog_policy_tag_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_data_catalog_policy_tag_iam_policy.this.id
}

output "this" {
  value = google_data_catalog_policy_tag_iam_policy.this
}
```

[top](#index)