# google_storage_transfer_project_service_account

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_storage_transfer_project_service_account" {
  source = "./modules/google/d/google_storage_transfer_project_service_account"

  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_storage_transfer_project_service_account" "this" {
  # project - (optional) is a type of string
  project = var.project
}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = data.google_storage_transfer_project_service_account.this.email
}

output "id" {
  description = "returns a string"
  value       = data.google_storage_transfer_project_service_account.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_storage_transfer_project_service_account.this.project
}

output "this" {
  value = google_storage_transfer_project_service_account.this
}
```

[top](#index)