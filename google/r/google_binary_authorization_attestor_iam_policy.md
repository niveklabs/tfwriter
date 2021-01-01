# google_binary_authorization_attestor_iam_policy

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
module "google_binary_authorization_attestor_iam_policy" {
  source = "./modules/google/r/google_binary_authorization_attestor_iam_policy"

  # attestor - (required) is a type of string
  attestor = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
variable "attestor" {
  description = "(required)"
  type        = string
}

variable "policy_data" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "google_binary_authorization_attestor_iam_policy" "this" {
  attestor    = var.attestor
  policy_data = var.policy_data
  project     = var.project
}
```

[top](#index)

### Outputs

```hcl
output "etag" {
  description = "returns a string"
  value       = google_binary_authorization_attestor_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_binary_authorization_attestor_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_binary_authorization_attestor_iam_policy.this.project
}

output "this" {
  value = google_binary_authorization_attestor_iam_policy.this
}
```

[top](#index)