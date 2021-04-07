# google_api_gateway_gateway_iam_policy

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
module "google_api_gateway_gateway_iam_policy" {
  source = "./modules/google-beta/r/google_api_gateway_gateway_iam_policy"

  # gateway - (required) is a type of string
  gateway = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "gateway" {
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

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_api_gateway_gateway_iam_policy" "this" {
  # gateway - (required) is a type of string
  gateway = var.gateway
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_api_gateway_gateway_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_api_gateway_gateway_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_api_gateway_gateway_iam_policy.this.project
}

output "region" {
  description = "returns a string"
  value       = google_api_gateway_gateway_iam_policy.this.region
}

output "this" {
  value = google_api_gateway_gateway_iam_policy.this
}
```

[top](#index)