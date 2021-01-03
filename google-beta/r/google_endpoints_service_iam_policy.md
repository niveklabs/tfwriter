# google_endpoints_service_iam_policy

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_endpoints_service_iam_policy" {
  source = "./modules/google-beta/r/google_endpoints_service_iam_policy"

  # policy_data - (required) is a type of string
  policy_data = null
  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_data" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "google_endpoints_service_iam_policy" "this" {
  policy_data  = var.policy_data
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_endpoints_service_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_endpoints_service_iam_policy.this.id
}

output "this" {
  value = google_endpoints_service_iam_policy.this
}
```

[top](#index)