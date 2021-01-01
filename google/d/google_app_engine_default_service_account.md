# google_app_engine_default_service_account

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
module "google_app_engine_default_service_account" {
  source = "./modules/google/d/google_app_engine_default_service_account"

  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```hcl
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "google_app_engine_default_service_account" "this" {
  project = var.project
}
```

[top](#index)

### Outputs

```hcl
output "display_name" {
  description = "returns a string"
  value       = data.google_app_engine_default_service_account.this.display_name
}

output "email" {
  description = "returns a string"
  value       = data.google_app_engine_default_service_account.this.email
}

output "id" {
  description = "returns a string"
  value       = data.google_app_engine_default_service_account.this.id
}

output "name" {
  description = "returns a string"
  value       = data.google_app_engine_default_service_account.this.name
}

output "project" {
  description = "returns a string"
  value       = data.google_app_engine_default_service_account.this.project
}

output "unique_id" {
  description = "returns a string"
  value       = data.google_app_engine_default_service_account.this.unique_id
}

output "this" {
  value = google_app_engine_default_service_account.this
}
```

[top](#index)