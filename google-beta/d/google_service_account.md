# google_service_account

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_service_account" {
  source = "./modules/google-beta/d/google_service_account"

  # account_id - (required) is a type of string
  account_id = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
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

### Datasource

```terraform
data "google_service_account" "this" {
  # account_id - (required) is a type of string
  account_id = var.account_id
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.google_service_account.this.display_name
}

output "email" {
  description = "returns a string"
  value       = data.google_service_account.this.email
}

output "id" {
  description = "returns a string"
  value       = data.google_service_account.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_service_account.this.name
}

output "unique_id" {
  description = "returns a string"
  value       = data.google_service_account.this.unique_id
}

output "this" {
  value = google_service_account.this
}
```

[top](#index)