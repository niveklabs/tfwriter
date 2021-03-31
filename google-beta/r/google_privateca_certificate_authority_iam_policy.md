# google_privateca_certificate_authority_iam_policy

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
module "google_privateca_certificate_authority_iam_policy" {
  source = "./modules/google-beta/r/google_privateca_certificate_authority_iam_policy"

  # certificate_authority - (required) is a type of string
  certificate_authority = null
  # policy_data - (required) is a type of string
  policy_data = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_authority" {
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
resource "google_privateca_certificate_authority_iam_policy" "this" {
  certificate_authority = var.certificate_authority
  policy_data           = var.policy_data
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_privateca_certificate_authority_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_privateca_certificate_authority_iam_policy.this.id
}

output "this" {
  value = google_privateca_certificate_authority_iam_policy.this
}
```

[top](#index)