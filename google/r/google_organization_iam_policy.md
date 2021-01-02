# google_organization_iam_policy

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_organization_iam_policy" {
  source = "./modules/google/r/google_organization_iam_policy"

  # org_id - (required) is a type of string
  org_id = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "org_id" {
  description = "(required) - The numeric ID of the organization in which you want to manage the audit logging config."
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
resource "google_organization_iam_policy" "this" {
  org_id      = var.org_id
  policy_data = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_organization_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_organization_iam_policy.this.id
}

output "this" {
  value = google_organization_iam_policy.this
}
```

[top](#index)