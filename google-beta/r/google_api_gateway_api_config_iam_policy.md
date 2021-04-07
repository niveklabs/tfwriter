# google_api_gateway_api_config_iam_policy

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
module "google_api_gateway_api_config_iam_policy" {
  source = "./modules/google-beta/r/google_api_gateway_api_config_iam_policy"

  # api - (required) is a type of string
  api = null
  # api_config - (required) is a type of string
  api_config = null
  # policy_data - (required) is a type of string
  policy_data = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "api" {
  description = "(required)"
  type        = string
}

variable "api_config" {
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

```terraform
resource "google_api_gateway_api_config_iam_policy" "this" {
  # api - (required) is a type of string
  api = var.api
  # api_config - (required) is a type of string
  api_config = var.api_config
  # policy_data - (required) is a type of string
  policy_data = var.policy_data
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = google_api_gateway_api_config_iam_policy.this.etag
}

output "id" {
  description = "returns a string"
  value       = google_api_gateway_api_config_iam_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_api_gateway_api_config_iam_policy.this.project
}

output "this" {
  value = google_api_gateway_api_config_iam_policy.this
}
```

[top](#index)